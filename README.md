## Notes

```swift
self.navigationItem.title = "my title" //sets navigation bar title.
self.tabBarItem.title = "my title" // sets tab bar title.
self.title = "my title" // sets both of these.


// CollectionView Layout
let layout = self.moviesCollectionView.collectionViewLayout as! UICollectionViewFlowLayout
let itemWidth = self.view.frame.width / 2
layout.sectionInset = UIEdgeInsetsMake(0, 0, 0, 0);
layout.minimumInteritemSpacing = 0
layout.minimumLineSpacing = 0
layout.itemSize = CGSize(width: itemWidth, height: (1.5 * itemWidth))
  

// Sort Date
movies.sort {
    item1, item2 in
    let data1 = item1[key] as! String
    let data2 = item2[key] as! String
    let date1 = dateFormatter.date(from: data1)
    let date2 = dateFormatter.date(from: data2)
    return date1! > date2!
}


// Transparent NavigationBar
self.navigationController?.navigationBar.setBackgroundImage(UIImage(), for: .default)
// Sets shadow (line below the bar) to a blank image
self.navigationController?.navigationBar.shadowImage = UIImage()
// Sets the translucent background color
self.navigationController?.navigationBar.backgroundColor = UIColor(red: 0.0, green: 0.0, blue: 0.0, alpha: 0.0)
// Set translucent. (Default value is already true, so this can be removed if desired.)
self.navigationController?.navigationBar.isTranslucent = true


// Scroll View Layout ignoring NavigationBar & BottomBar
self.automaticallyAdjustsScrollViewInsets = false


// Animation
UIView.animate(withDuration: 1.0, animations: {
    subView.alpha = 0
}, completion: { (finished: Bool) -> Void in
    subView.removeFromSuperview()
})


// Round Angle
contentView.layer.masksToBounds = true
contentView.layer.cornerRadius = radius


// Blur View
let blurEffect = UIBlurEffect(style: UIBlurEffectStyle.dark)
let blurView = UIVisualEffectView(effect : blurEffect)
blurView.frame = moviePostImg.bounds
image.addSubview(blurView)


// Geture : Tap outside to hide
var tapGesture = UITapGestureRecognizer()
func whenGestureNeeded () {
    tapGesture = UITapGestureRecognizer(target: self, action: #selector(MoviesViewController.autoHideWhenTapOutside(sender: )))
        viewTapped.addGestureRecognizer(tapGesture)
    }
}
func autoHideDropdownWhenTapOutside(sender: UITapGestureRecognizer) {
    hideTargetView()
    viewTapped.removeGestureRecognizer(tapGesture)
}


// prevent delay on NavigationBar Appearance when going back to parent controller
override func willMove(toParentViewController parent: UIViewController?) {
    if parent == nil {
        // The view is being removed from the stack, so call your function here
        UIHelper.transparentNavigationBar(sender: self)
    } else {
        UIHelper.restoreNavigationBar(sender: self)
    }
}

```

```
/**
Error #1: Apple Mach-O Linker Error: Linker command failed with exit code 1
Quit Xcode
Restart the System
Select Xcode -> Preferences.
This will open a pop-up window. Select 'Locations'. In Locations, you will see 'Derived Data'. Click on the arrow icon right next to the path.
This will open a folder containing 'Derived Data', delete it.
Clean the Product and Run
*/
```

