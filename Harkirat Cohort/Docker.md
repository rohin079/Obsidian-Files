![[Pasted image 20241015223649.png]]

![[Pasted image 20241015224918.png]]

![[Pasted image 20241017204248.png]]

![[Pasted image 20241020212356.png]]

these layers are cached so that whenever we are rebuilding our dockerfile the layers which are cached can directly be used.

when we create our dockerfile we want that the number of cached layers are as much as possible, if we change anything in a certain step, the layers above that step remain cached and all layers below become un-cached and have to be executed again. 

that is why:
![[Pasted image 20241020222604.png]]

now since we dont change dependencies that often, it would be optimal to first copy and cach copying package.json layer and then since npm install will only run when package.json changes after the first time, this layer will get cached for a longer time.

the step that changes the most is kept at the very end : eg your source code



