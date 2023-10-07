graphcore
    - IPUs (Intelligence processing units) 
        + new processor designed for Ai compute. unique architecture 
        + 1000x more processing power than the phone. 
        + 59.4bn transistors. 
        + 1472 cores
            + each can run 9000 parallel program threads
        + 900mb in-processor memory
        + 250 tFLOPS @ FP16.16 and FP16.SR (stochastic rounding) of AI compute
            ~ stochastic rounding: first we had deterministic rounding. rounds up or
              down with equal probability 1/2.
            ~ the summit (IBM) Nov 2018 143.4 pFLOPS. capable of upto 200 pFLOPS
            ~ M1 GPU has 2.6 tFLOPS. M1 pro 10.4 tFLOPS. M1 ultra 21 tFLOPS.
        $ financials
            $ {oct 2016}  $32mn in Series A by Bosch. dell technologies, samsung, *amadeus capital*,
                          *C4 Ventures*, *draper esprit*, *pitango*, *foundation capital*
            $ {jul 2017}  $32mn in Series B by *Atomico*. Greg Vrockman, Ilya Sutskever 
            $ {nov 2017}  $50mn in Series C by Sequoia. 
            % {jul 2018}  Ship IPU early access 
            $ {dec 2018}  $200mn in Series D. BMW, Microsoft, *Chrysalis*, *Sofina*. valued at $1.7bn 
            % {nov 2018}  IPU products officially lainched. IPUs to rent on Azure and buy from dell.
            $ {feb 2020}  $150mn in Series D2. valued at $1.95bn. *baillie gifford*, *mayfair equity*
                          *M&G investments*, *Merian Chrysalis*
            % {jul 2020}  second generation IPU. IPU M2000 powered by MK2 GC200 IPU 8x step up.
            % {sep 2020}  partner program "to serve customers around the world"
            $ {dec 2020}  prod ver of pytorch. enabling pytorch programs to run on IPU. 
            $ {dec 2020}  $222mn in series E funding led by *ontario teachers' pensions plan board*
                          valued at $2.77bn. *fidelity international*, *schroders*, *baillie gifford*,
                         *draper esprit*


[A reading about stochastic rounding](https://nhigham.com/2020/07/07/what-is-stochastic-rounding/)
[Stochstic Rounding: Algorithms and Hardware Accelerator](https://arxiv.org/pdf/2001.01501.pdf)
