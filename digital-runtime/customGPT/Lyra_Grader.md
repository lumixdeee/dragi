


Baseline grader: [https://chatgpt.com/g/g-6a32c04cf584819192c6699f7e8562a4-lyra-prompt-grader-copy]  
This is still a full Nexus-based grader organism, but with changed Utilities Core in that copy back to v11.  
So this baseline does not include the object-custody / MOGRI / DRAGI.  
That means you can test your principle against it.
Open a chat with the baseline, upload whatever MOGRI/DRAGI files or test cases you want, and see how it behaves.  
The second one is the newer grader:  
[[Current grader](https://chatgpt.com/g/g-6890473e01708191aa9b0d0be9571524-lyra-prompt-grader)]  
That one already has the object-custody/proxy-drift lock built in.  
The comparison would be:  
baseline without your lock  
baseline + your files uploaded in chat  
current version with the lock already integrated  
The main thing to test is whether the grader keeps judging the declared object, or if it drifts into proxy rewards like polish, elegance, structure density, self-test appearance or coverage.  

