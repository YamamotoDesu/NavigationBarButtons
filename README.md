# [NavigationBarButtons](https://www.youtube.com/watch?v=xDJ8eIYih1k)
Customizing, and managing button items across multiple view controllers.

<img width="490" src="https://github.com/YamamotoDesu/NavigationBarButtons/blob/main/NavigationBarItems/Gif/NavigationBarButtons.gif">

<img width="493" src="https://user-images.githubusercontent.com/47273077/156865055-dc43566f-3414-4469-aaa3-68107c22794d.png">

## How to set up
```swift
import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        
        title = "Bar Items"
        view.backgroundColor = .systemBlue
        
        let button = UIButton(frame: CGRect(x: 0, y: 0, width: 200, height: 50))
        view.addSubview(button)
        button.center = view.center
        button.backgroundColor = .systemTeal
        button.setTitle("Go To View 2", for: .normal)
        button.addTarget(self, action: #selector(didTapButton), for: .touchUpInside)
        
        navigationController?.navigationBar.tintColor = .label
        
        
        confiureItems()
    }
    
    private func confiureItems() {
        self.navigationItem.rightBarButtonItems = [
            UIBarButtonItem(
                barButtonSystemItem: .add,
                target: self,
                action: nil
            ),
            UIBarButtonItem(
                image: UIImage(systemName: "person.circle"),
                style: .done,
                target: self,
                action: nil
            ),
        ]
        
        self.navigationItem.leftBarButtonItem = UIBarButtonItem(
            image: UIImage(systemName: "gear"),
            style: .done,
            target: self,
            action: nil
        )
        
    }
    
    @objc func didTapButton() {
        let vc = UIViewController()
        vc.title = "View 2"
        vc.view.backgroundColor = .systemGreen
        vc.navigationItem.rightBarButtonItem = UIBarButtonItem(title: "Sign Out",
                                                               style: .done,
                                                               target: self,
                                                               action: nil)
        navigationController?.pushViewController(vc, animated: true)
    }
}



```
