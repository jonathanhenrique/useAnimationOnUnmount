# useAnimationOnUnmount
## React custom hook that allows animation on an unmount event

The hook returns two function (open, close) for triggering the opening and the closing of the component and two boolean values (isOpen, isRunningAnimation). You will be able to trigger a CSS transition injecting a class to your component whenener the isRunningAnimation is true and then unmount it when isOpen is false.

###Example:
```javascript
function Modal ({children}){
  const { open, close, isOpen, isRunningAnimation } = useAnimationOnUnmount({
    isMounted: false, /* If you pass isMounted true isOpen will be true on the initial render, by default it will be false */
    delay: 350, /* You can define the delay you want */
  });

  if (!isOpen && !isRunningAnimation) return null; /* If not open and if is not running the animation then it will be unmounted */

  /* You will trigger the unmount animation by injecting a class to your component using the value of the isRunningAnimation */
  return <div onClick={close} className={isRunningAnimation ? 'toClose' : ''}>{children}</div>;
}
```
