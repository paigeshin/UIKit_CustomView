# UIKit_CustomView

```swift

import UIKit

class CustomView: UIView {
    let imageView: UIImageView = {
        let view = UIImageView()
        view.translatesAutoresizingMaskIntoConstraints = false
        view.image = UIImage(systemName: "star")
        return view
    }()

    let descriptionLabel: UILabel = {
        let label = UILabel()
        label.translatesAutoresizingMaskIntoConstraints = false
        label.text = "My Favorite Quote"
        label.textColor = .white
        return label
    }()

    override init(frame: CGRect) {
        super.init(frame: frame)
        setupView()
    }

    // If you load view from storyboard
    // If you load view programmatically, this own't be loaded
    required init?(coder: NSCoder) {
        super.init(coder: coder)
        setupView()
    }

    func setupView() {
        backgroundColor = .brown
        addSubview(imageView)
        addSubview(descriptionLabel)

        NSLayoutConstraint.activate([
            imageView.widthAnchor.constraint(equalToConstant: 24),
            imageView.heightAnchor.constraint(equalTo: imageView.widthAnchor),
            imageView.leadingAnchor.constraint(equalTo: leadingAnchor, constant: 12),
            imageView.centerYAnchor.constraint(equalTo: centerYAnchor),
            descriptionLabel.leadingAnchor.constraint(equalTo: imageView.trailingAnchor, constant: 12),
            descriptionLabel.trailingAnchor.constraint(equalTo: trailingAnchor, constant:  -12),
            descriptionLabel.topAnchor.constraint(equalTo: topAnchor, constant: 16),
            descriptionLabel.bottomAnchor.constraint(equalTo: bottomAnchor, constant: -16)
        ])
    }

}


```
