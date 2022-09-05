## Sasto Tickets SDK Integration summary for Namaste Pay ( IOS )

<br>
<br>

Minimum SDK Requirement: IOS 14


#### Steps to add SDK to your project

1. Open your project in Xcode

2. Go to File > Add Packages...

3. In the field Enter package repository URL, enter "https://github.com/app-sastotickets/ios-namastepay-live.git"

4. Pick the latest version and Add Package.

#### Initializing SDK

1. Import SwiftUi & Sastotickets in the controller file from where we are going to initilize sastotickets sdk :

```
import SwiftUI
import SastoTickets
        
```

2. Run the following code preferably on button click which will display sastotickets user interface

```
let vc = UIHostingController(rootView:SastoticketsView(clientId: "", clientSecret: "", walletBalance: 0, phone: ""){response, error in
    if error != nil {
        //Handle error
    }
    if response != nil {
        //Do something with response
    }
    })
vc.modalPresentationStyle = .fullScreen
present(vc, animated: true)

```


#### Usage Example
ViewController.swift

```
import UIKit
import SwiftUI
import SastoTickets


class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        
        let button = UIButton(frame: CGRect(x: 0, y: 0, width: 220, height: 50))
        view.addSubview(button)
        button.center = view.center
        button.setTitle("Show sdk", for: .normal)
        button.backgroundColor = .systemRed
        button.addTarget(self, action: #selector(didTapButton), for: .touchUpInside)
        
        
    }
    
    @objc func didTapButton(){
        let vc = UIHostingController(rootView:SastoticketsView(clientId: "", clientSecret: "", walletBalance: 0, phone: ""){response, error in
            if error != nil {
                //Handle error
            }
            if response != nil {
                //Do something
            }
        })
        vc.modalPresentationStyle = .fullScreen
        present(vc, animated: true)
        
    }

}
        
```
