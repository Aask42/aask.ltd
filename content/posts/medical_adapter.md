+++
title = 'Medical_adapter'
date = 2023-10-27T11:59:06-05:00
draft = false
+++

## Union Medico Autoinjector Adapter

One of the things I have to do regularly to maintain my health is take an injeciton intramuscularly once a week. While many are okay just doing this free hand, and others go in to their doctor's offices to get it done, I picked up a <a href="https://unionmedico.com/product-category/auto-injector-90/">Union Medico autoinjector</a>. It's actually pretty cool, it holds a standard syringe and drops it in to the muscle at the same pressure every time. Yes I still have to fill the syringe and prep it for use, but this tool has been a LIFE SAVER literally. While it wasn't super expensive and has made my life better every week of my life for the last two years, it has a limitation that it *only takes one style* of BD Luer-Lok syringe.

<img src="/images/auto_injector.png" style="width:100%" alt="Horizontal long silver cylindrical device with outer sheath that moves left and right, there's a locking rihg under the button that must be depressed to relese the outer spring-loaded sheath + needle in to the skin"></img>

Sadly, my pharmacy is out of compatible syringes meaning I would have to go out in the world and find my own supply while waiting for the backorder to come in. This led to me picking up a bunch of what I thought were compatible syringes in bulk off of Amazon. Unfortuantely, the Amazon product is **too small** for my auto-injector. Probably should have looked for one with a picture of the syringe on it but even then scrolling endlessly yielded few results. I had to give up and wait for the pharmacy or find another online shop that can't deliver overnight (I was leaving on a 2 week trip two days from then). I had to just give up searching online, I can't get the correct style I need in the timeline I need it. Protip, if there's not a picture of what's on the box, it's probably the wrong kind. 

<img src="/images/syringe_box.png"  style="width:50%" alt="Box for syringes with no picture of the actual thing in the box"></img>

Now there I was sitting with 100 of the wrong size tube for my autoinjector with a need to take my meds before leaving in a couple days. How to get this to work... should be only a simple cylindrical adapter right? Only two cylinders and a cutout for the center, as well as a cutout for attaching to the Amazon mistake. With an idea in mind I turned to OpenSCAD, calipers, and my AnkerMake M5 with some PLA filament in the drybox. Let's get this thing designed! The design was really easy to make, coming in at 10 lines of OpenSCAD and ~~is going to~~ has already saved me a world of hurt not being able to actually take my medicine. 

```openscad
translate([0,0,shank_length]) difference(){
    cylinder(head_length, head_r, head_r);
    #cylinder(head_length, hull_r, hull_r);
        #cube([8,8,head_length]);
}
difference(){
cylinder(shank_length,shank_r, shank_r);
    #cylinder(shank_length, hull_r, hull_r);
    #cube([8,8,shank_length]);
}
```

Now I know OpenSCAD can be a little daunting. When I asked a friend about switching to FreeCAD they said it was clunky, and I asked if it was worth switching off of OpenSCAD to learn it. His reply was distain and calling me a monster. It's funny because he even works at a 3d print shop! Just so you're not so scared of it, this is what the UX for OpenSCAD looks like:

<img src="/images/openscad_screenshot.png" style="width:100%;" alt="Screen shot of the OpenSCAD interface. There is a code-input panel on the left and rendered 3d object on the right. Object is the designed part which is a cylinder long enough to mount on the sheath around the previously mentioned picture of the autoinjector."></img>

Once designed, let's print it! After printing, you can see the new adapter part next to the syringe. 

<img src="/images/autoinjector_with_syringe.png" style="width:100%" alt="Amazon syringe, printed adapter, and autoinjector horizontally lined up"></img>

It fits in to the autoinjector, success! Now I won't have to do it manually which is a huge mental block for me. 

<img src="/images/adapter_test_fit.png"  style="width:100%" alt="Adapter dry-fit in to autoinjector"></img>

And makes a NICE snapping sound when clicking in to place, as well as comes off easily after use. Does this mean my next 3d printer might be HSA eligible? Not sure, but my current one is already helping with my healthcare. 

<img src="/images/adapter_with_syringe_in_autoinjector.png"  style="width:100%" alt="Adapter mounted on unfilled syringe in autoinjector"></img>

## Conclusion

This was a really simple solution to a problem I had in my life that only a tech mindset and a 3d printer could solve in real time as I needed. If I had not had the skills to design my own parts on OpenSCAD, the hardware to print the part, and the knowhow of basic clip-fit parts for pipes from my plumbing upbringing, I may not have been able to solve this challenge to my own healthcare. It's amazing how small changes to seemingly small things can have big impact to even my own life. It's even more amazing that in our generation if we want to look for them, we can find the tools and knowledge needed to overcome just about any roadblock that might present itself in our lives. 

PS: If you have to take any kind of injections on the regular, GET AN AUTOINJECTOR LIKE THIS. They save so much headache and provide a consistent experience every time you have to use them. And, while one of the parts on my model keeps breaking, I've been able to repair it after they've sent multiple replacement parts and every one breaks in the same exact way. They do keep overnighting replacements when I ask though ;). Will probably do a writeup on that later. 


