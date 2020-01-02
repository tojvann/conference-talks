# Zen and the Art of Learning Assembler in the 21st Century

[link](https://www.youtube.com/watch?v=zWGn3kMz3rU)

### Things we assume in this modern world of computing

- __Infinite Memory__: We have got automatic memory allocation and deallocation, memory paging, garbage collection i.e. we need not worry about the free memory anymore. We need not worry about the memory anymore it will be taken care by itself.
- __Infinite Storage__: In this modern world of computing we have got Tera-bytes of disk storage that to really fast storage with the introduction of SSD (Solid State Disks) . We have also got exa-bytes of cloud storage with the advent of cloud computing.
- **Infinite Performance**: We have got Multi-core threading, fibres, concurrency, serverless computing. Today we have got many efficient chips embedded in a single system.
- __Infinite Bandwidth__: Gigabit fibre connection. We don't think these days about bandwidth consumption because most of the stuff these days like api, apps the amount of data is so small compared to the bandwidth.



> A metaphor is a kind of lie to help people understand what's true.
>
> -- Terry Pratchett



Modern languages are magical, they do things which unless you have a very deep understanding look magical.

### Language Generations

-  __5th Generation Languages__ JDWIM (Just Do What I Mean). 
  - In this fictional computing lanaguage you are not instructing the computer what it is that you want to do. You are rather instructing the computer that you want to do a thing, and it's the computer's job to find out what that thing is and how to do it and present the results.
- __4th Generation Languages__: Python, Ruby, SQL
  - We explicitly specify the computer to do a particular thing and it is upto the computer to figure out how to do it. SQL is a good example for this case, you give an instruction in english language and the computer executes it and presents you with the output/results.
- __3rd Generation Languages__: C, C++, C#, Java, BASIC, Pascal
  - In these languages you tell the machine what you want to happen, on the top of it you also tell it how to do it. But we are still talking in terms of abstract in case of 3rd Generation of languages i.e. object orientation.
- __2nd Generation Languages__: Assembly Languages
  - 2nd Generation languages are representational forms of the actual bytes the machine is executing.
- __1st Generation Languages__: Machine Language (x86, amd64, arm)
  - 1st Generation languages are the actual bytes running on the actual memory which the machine is executing.



### Rain Dance Programming

You learn to do a rain dance and it rains. Now, you learn to do the rain dance really well. Now you start to modify the steps of your rain dance for different types of rains. All your effort to learn rain dance is nice until one day it doesn't rain anymore. 

You don't have a fundamental understanding of what you are doing. Some day something will go wring which is beyond your control.



In the 21st century we think of the 3rd level language as the foundation into our journey in programming but we don't take into account a very important underlying fact that these languages are magical to an extent.

We should start learning the underlying concepts that make the constructs of the 3rd Generation Languages a reality in this 21st Century.  We live in a world with a lot of magic the above sense. It is one of the reason why Modern Software can be _Problematic, Slow, Inaccurate, Faulty_ .

We don't actually need people to code in an assembler but rather live in a world with magic which people can really understand.



> # Learning Assembler changes how you think.



We can consider the case of IoT devices since they are basic in terms of constructs. When we go to the micro-controller level, we have to think about stuff like __constraints of memory, constraints of power of device__. This changes the way how you think because after all _Constraints are good_ in this case. If you are able to code at this level you are not thinking magically, you are not just doing rain dance you are building up fundamentals overall. You need to understand what is going on and build it from the scratch yourself,  even though there are libraries to do it. Learning assembler will change your thinking so that even if you are able to use something that someone has done you will understand truly whats happening beneath.



### Minimalism is GOOD

If you are used to working on machines which are running single core that too on a low Mega Hertz clock cycle, you are thinking everything efficient, not because it is a good idea but you have got no choice. Efficiency in this case becomes a necessity. If you don't make a program that small and that effective in this particular case things will not work. You will learn how to structure your code a lot better, you are going to think about the real structures of what is going on. This means less code and less code == less bugs.



> ## Less Code == Less BUGS
>
> ## Simplicity ∝ Maintainability
>
> ## Performance is a Function of Deep Understanding







Every language that you learn will actually make you a better programmer in every other language that you know. Every new language that you learn corrects your abstracts, it moves your concepts away from specific implementations, and specific implementation patterns, it allows you to think about things in different ways.





This is what i understood from a talk given by

TOM CULLY
[Zen and the Art of Learning Assembler in the 21st Century](https://2019.linux.conf.au/schedule/presentation/256/)



He could be contacted at tom@blackraven.co.nz



### 



