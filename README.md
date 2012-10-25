HTDelegateProxy
===============

# Overview

HTDelegateProxy is an NSProxy subclass that allows you to assign multiple delegates to a single source.

# Installation

### Cocoapods users:
Add the following line to your Podfile: <br/>
pod 'HTDelegateProxy', '~> 0.0.1'

### Everyone else:
Add the HTDelegateProxy.m/h files to your project.

# Usage

Delegates are not retained, so you have to maintain a strong reference to your HTDelegateProxy instance. <br/>
### In your interface: <br/>
    
    #import "HTDelegateProxy.h"
    ...
    @property (nonatomic, strong) UIScrollView *scrollView;
    @property (nonatomic, strong) HTDelegateProxy *delegateProxy;
    ...

### In your class:

    ...
    self.scrollView = [[UIScrollView alloc] init];
    self.delegateProxy = [[HTDelegateProxy alloc] init];
    self.delegateProxy.delegates = @[firstDelegate, secondDelegate];
    self.scrollView.delegate = (id)self.delegateProxy;
    ...


    