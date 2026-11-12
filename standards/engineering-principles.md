# Engineering principles

- **High cohesion, low coupling:** group code by responsibility and change boundary. Do not split solely to reduce line count.
- **Explicit state ownership:** keep page state local unless multiple distant consumers genuinely need shared state. Prefer props down and events up for component boundaries.
- **Container and presentation separation:** extract UI regions when they have independent behavior, complexity, reuse, or a clear contract. Do not enforce this mechanically.
- **Simple abstractions:** introduce an abstraction when it removes meaningful duplication or isolates a volatile dependency.
- **Incremental refactoring:** preserve behavior, make small changes, and run relevant tests after each meaningful extraction.
- **Errors are part of the design:** distinguish validation, authorization, conflict, rate-limit, network, and server failures.
- **Security by default:** never commit secrets; minimize token scopes; validate untrusted input at boundaries.
- **Evidence-based optimization:** measure performance and complexity before changing them.
- **Documentation as an interface:** document setup, module responsibilities, component contracts, and operational procedures.
