# Clean-Swift-Templates
Ready to use Xcode templates for Uncle Bob's Clean Swift architecture with additional added improvement in a form of builder object which connects all necessary entities.
# How to add templates to Xcode
Navigate to templates folder in the Terminal and execute `make install_templates`
# Dip Module
Dip Module template needs [Dip](https://github.com/AliSoftware/Dip) and implementation of `ResolvableConfigurator`
```
import Dip

open class ResolvableConfigurator: Resolvable {
    // MARK: - Public Properties
    public var container: DependencyContainer {
        guard let container = injectedContainer else {
            fatalError("This can't happen")
        }

        return container
    }

    // MARK: - Private Properties
    private var injectedContainer: DependencyContainer?

    // MARK: - Initializers
    public init() { }

    // MARK: - Public Methods
    public func resolveDependencies(_ container: DependencyContainer) {
        self.injectedContainer = container
    }

    public func didResolveDependencies() { }
}
```
