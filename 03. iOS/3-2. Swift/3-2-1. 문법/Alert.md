Alert 

과제를 진행하면서 새로운 기능 구현을 위해 Alert 를 알아보았습니다. 

우선 사용자 액션을 통해 
알림창을 띄워 주는 기능 인데 완벽하게 기능구현을 숙지 하지 못해서 구글링의 도움음 받아 코드를 강제(?)적으로 완성 시켰습니다. 

우선 오늘은 구글이 알려준(??) 코드를 보고 이후에 찬찬히 복습하는 개념을 가져가 보겠습니다. 

 ```SWIFT
 
import UIKit

class BurgerViewController: UIViewController, UICollectionViewDelegate, UICollectionViewDataSource, UICollectionViewDelegateFlowLayout {
    
    @IBOutlet weak var BurgerCollectionView: UICollectionView!
    
    func collectionView(_ collectionView: UICollectionView, layout collectionViewLayout: UICollectionViewLayout, sizeForItemAt indexPath: IndexPath) -> CGSize {
        // 여기에서 원하는 셀의 크기를 지정합니다. 예를 들어, 가로 100, 세로 100으로 설정하겠습니다.
        return CGSize(width: 300, height: 250)
    }
    
    // 데이터가 몇개인지
    func collectionView(_ collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int {
        return 4
    }
    
    // 데이터가 무엇인지
    func collectionView(_ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath) -> UICollectionViewCell {
        
        let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "MenuCollectionViewCell", for: indexPath) as! MenuCollectionViewCell
        
        let menuList = ["BulgogiBurger", "CheeseBurger", "ChickenBurger", "ShrimpBurger"]
        let currentMenu = menuList[indexPath.row]
        
        cell.setup(with: currentMenu, menuName: currentMenu)
        
        // cell.MenuImage.contentMode = .scaleAspectFit
        
        cell.MenuImage.contentMode = .scaleAspectFit
        
        cell.layer.cornerRadius = 8
        cell.backgroundColor = UIColor.init(cgColor: #colorLiteral(red: 1, green: 0.7779013515, blue: 0.4334530234, alpha: 0.8470588235))
        
        // 이미지뷰에 탭 제스처 추가
               let tapGestureRecognizer = UITapGestureRecognizer(target: self, action: #selector(menuImageTapped))
               cell.MenuImage.addGestureRecognizer(tapGestureRecognizer)
               cell.MenuImage.isUserInteractionEnabled = true
        
        return cell
    }
    
    @objc func menuImageTapped(sender: UITapGestureRecognizer) {
        // 수량 조절을 위한 스테퍼 생성
        let stepper = UIStepper()
        stepper.minimumValue = 1
        stepper.maximumValue = 10
        stepper.value = 1
        stepper.autorepeat = true
        stepper.translatesAutoresizingMaskIntoConstraints = false

        // 수량을 표시할 레이블 생성
        let quantityLabel = UILabel()
        quantityLabel.text = "수량: \(Int(stepper.value))"
        quantityLabel.translatesAutoresizingMaskIntoConstraints = false

        // 알림창 생성
        let alert = UIAlertController(title: "장바구니에 추가", message: "\n\n\n", preferredStyle: .alert)
        
        // 스테퍼와 수량 레이블을 알림창에 추가
        alert.view.addSubview(stepper)
        alert.view.addSubview(quantityLabel)


        // 수량 레이블 위치 설정
        quantityLabel.centerXAnchor.constraint(equalTo: alert.view.centerXAnchor).isActive = true
        quantityLabel.topAnchor.constraint(equalTo: alert.view.topAnchor, constant: 50).isActive = true

        // 스테퍼 위치 설정
        stepper.centerXAnchor.constraint(equalTo: alert.view.centerXAnchor).isActive = true
        stepper.topAnchor.constraint(equalTo: quantityLabel.bottomAnchor, constant: 6).isActive = true

        // 스테퍼 값이 변경될 때마다 수량 레이블 업데이트
        stepper.addTarget(self, action: #selector(stepperValueChanged), for: .valueChanged)

        // 예 버튼 추가
        alert.addAction(UIAlertAction(title: "추가하기", style: .default, handler: { action in
            self.addToCart() // 수량을 인자로 전달하여 장바구니에 추가하는 로직 호출
        }))
        
        // 아니오 버튼 추가
        alert.addAction(UIAlertAction(title: "취소", style: .cancel, handler: nil))
        
        // 알림창 표시
        present(alert, animated: true, completion: nil)
    }

    @objc func stepperValueChanged(sender: UIStepper) {
        // 스테퍼 값이 변경될 때마다 수량 레이블 업데이트
        if let alert = self.presentedViewController as? UIAlertController,
           let quantityLabel = alert.view.subviews.last as? UILabel {
            quantityLabel.text = "수량: \(Int(sender.value))"
        }
    }

    func addToCart() {
        // 여기에 수량을 이용하여 실제로 장바구니에 추가하는 로직을 구현
        print("장바구니에 제품이 추가되었습니다.")
    }

    
    //여기 주석부분은 단순히 수량 없이 장바구니에 추가되었다고 알림창이나오는 버전입니다.
    //이부분 구현 방법을 몰라서 남들 코드 긇어와서.. 이부분은 장바구니에 추가하는 로직 구현할때 편리한 방법으로 채택해야 할것 같습니다.
    
//    @objc func menuImageTapped(sender: UITapGestureRecognizer) {
//           // 이미지를 누르면 "장바구니에 추가 하시겠습니까?" 다이얼로그를 띄우기
//           let alert = UIAlertController(title: "장바구니에 추가", message: "장바구니에 추가 하시겠습니까?", preferredStyle: .alert)
//           
//           // 예 버튼 추가
//           alert.addAction(UIAlertAction(title: "예", style: .default, handler: { action in
//               self.addToCart() // 실제로 장바구니에 추가하는 로직을 호출하는 함수
//           }))
//           
//           // 아니오 버튼 추가
//           alert.addAction(UIAlertAction(title: "아니오", style: .cancel, handler: nil))
//           
//           // 다이얼로그 표시
//           present(alert, animated: true, completion: nil)
//       }
//       
//       func addToCart() {
//           // 여기에 실제로 장바구니에 추가하는 로직을 구현
//           print("장바구니에 제품이 추가되었습니다.")
//       }
    
    // 여기에 viewDidLoad 추가
    override func viewDidLoad() {
        super.viewDidLoad()
        
        BurgerCollectionView.delegate = self
        BurgerCollectionView.dataSource = self
    }
}
```

이코드는 셀렉션 뷰를 이용해 버거메뉴를 보여주고 
사용자가 메뉴를 클릭시 Alert 를 이용해 알림창 을 띄워주는 코드입니다. 

사용자가 메뉴를 눌렀을때 나오는 Alert 에 수량과 +,- 스테퍼를 추가 하고 싶어서 코드가 복잡해 졌는데 이것을 
완벽하게 숙지할 수있도록 추후... 다시 알아보는 시간을 가져야 할 것 같습니다. 