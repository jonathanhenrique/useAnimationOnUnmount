# useAnimationOnUnmount
## React custom hook that allows animation on an unmount event

The hook returns two function (open, close) for triggering the opening and the closing of the component and two boolean values (isOpen, isRunningAnimation). You will be able to trigger a CSS transition injecting a class to your component whenener the isRunningAnimation is true and then unmount it when isOpen is false.
