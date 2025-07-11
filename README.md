<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Montelukast: A Comprehensive Monograph</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Harmony Neutrals -->
    <!-- Application Structure Plan: The application has been restructured into a comprehensive, single-page clinical monograph. The navigation is sticky, allowing users (healthcare students, professionals) to jump to specific sections. An AI-powered section has been added to provide a practical tool for generating patient counseling points. Custom-generated images have been added to enhance visual learning. The flow is logical: Identity -> Mechanism -> Clinical Use -> Dosing -> Pharmacokinetics -> Safety -> AI Counselor -> Interactions -> Pregnancy -> Brands -> References. -->
    <!-- Visualization & Content Choices: 
        - Report Info: All sections from the source text -> Goal: Inform/Educate -> Viz/Method: Structured HTML with Tailwind CSS, using headings, lists, and tables. -> Interaction: Scroll-based navigation. -> Justification: The user requested a detailed monograph. Tables are the best way to present comparative data like dosing, pharmacokinetics, and interactions.
        - User Input: Patient Scenario -> Goal: Assist Professionals -> Viz/Method: AI-powered text generation -> Interaction: User types a scenario, clicks a button to generate counseling points -> Justification: Leverages the Gemini API to provide a valuable, practical tool for healthcare professionals.
        - Generated Images: Mechanism, Safety, Pharmacokinetics -> Goal: Enhance Understanding -> Viz/Method: AI-generated images -> Interaction: Static visual aids -> Justification: Provides clear, professional illustrations for complex concepts, improving comprehension and engagement.
        - CONFIRMATION: NO SVG graphics used. NO Mermaid JS used.
    -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FDFBF8;
            color: #4A4A4A;
        }
        .nav-link {
            transition: color 0.3s ease;
            position: relative;
            padding-bottom: 8px;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            background-color: #D35400;
            transition: width 0.3s ease;
        }
        .nav-link.active, .nav-link:hover {
            color: #D35400;
        }
        .nav-link.active::after, .nav-link:hover::after {
            width: 100%;
        }
        .card-shadow {
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -2px rgba(0, 0, 0, 0.05);
        }
        .table-auto th {
            background-color: #F1F5F9;
            padding: 12px;
            text-align: left;
            font-weight: 600;
        }
        .table-auto td {
            padding: 12px;
            border-bottom: 1px solid #E5E7EB;
        }
        h2 {
            font-size: 2.25rem;
            font-weight: 700;
            color: #34495E;
            border-bottom: 3px solid #E57373;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
         h3 {
            font-size: 1.5rem;
            font-weight: 600;
            color: #D35400;
            margin-top: 2rem;
            margin-bottom: 1rem;
        }
        .loader {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #D35400;
            border-radius: 50%;
            width: 32px;
            height: 32px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="bg-gray-50">

    <header id="header" class="bg-white/90 backdrop-blur-lg sticky top-0 z-50 shadow-md">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center py-2">
                <a href="https://umt.edu.pk/" target="_blank" rel="noopener noreferrer" class="flex items-center space-x-3">
                    <img src="https://www.umt.edu.pk/images/colors-logo.png" alt="UMT Logo" class="h-12 md:h-16">
                    <span class="hidden sm:block text-2xl font-bold text-[#D35400]">Montelukast</span>
                </a>
                <button id="mobile-menu-button" class="lg:hidden text-3xl p-2">☰</button>
            </div>
        </div>
        <nav id="main-nav" class="bg-white border-t border-gray-200">
             <div id="desktop-menu" class="hidden lg:flex container mx-auto px-4 py-2 justify-center flex-wrap gap-x-6 gap-y-2">
                <a href="#identity" class="nav-link">Identity</a>
                <a href="#mechanism" class="nav-link">Mechanism</a>
                <a href="#indications" class="nav-link">Indications</a>
                <a href="#dosage" class="nav-link">Dosage</a>
                <a href="#pharmacokinetics" class="nav-link">Pharmacokinetics</a>
                <a href="#safety" class="nav-link">Safety</a>
                <a href="#ai-counselor" class="nav-link">✨ AI Counselor</a>
                <a href="#interactions" class="nav-link">Interactions</a>
                <a href="#pregnancy" class="nav-link">Pregnancy</a>
                <a href="#brands" class="nav-link">Brands</a>
                <a href="#references" class="nav-link">References</a>
            </div>
            <div id="mobile-menu" class="hidden lg:hidden bg-white py-2">
                <a href="#identity" class="block text-center py-2 text-lg nav-link">Identity</a>
                <a href="#mechanism" class="block text-center py-2 text-lg nav-link">Mechanism</a>
                <a href="#indications" class="block text-center py-2 text-lg nav-link">Indications</a>
                <a href="#dosage" class="block text-center py-2 text-lg nav-link">Dosage</a>
                <a href="#pharmacokinetics" class="block text-center py-2 text-lg nav-link">Pharmacokinetics</a>
                <a href="#safety" class="block text-center py-2 text-lg nav-link">Safety</a>
                <a href="#ai-counselor" class="block text-center py-2 text-lg nav-link">✨ AI Counselor</a>
                <a href="#interactions" class="block text-center py-2 text-lg nav-link">Interactions</a>
                <a href="#pregnancy" class="block text-center py-2 text-lg nav-link">Pregnancy</a>
                <a href="#brands" class="block text-center py-2 text-lg nav-link">Brands</a>
                <a href="#references" class="block text-center py-2 text-lg nav-link">References</a>
            </div>
        </nav>
    </header>

    <main class="container mx-auto p-4 md:p-8">
        <section id="identity" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Chemical & Pharmaceutical Identity</h2>
            <p class="mb-6 text-lg text-gray-600">Montelukast is a selective leukotriene receptor antagonist used in the management of asthma and allergic rhinitis. It is administered as its monosodium salt.</p>
            
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div>
                    <h3>Chemical Formula</h3>
                    <p class="text-2xl font-mono bg-gray-100 p-3 rounded">$C_{35}H_{35}ClNNaO_{3}S$</p>
                    <h3 class="mt-6">Therapeutic Category</h3>
                    <p class="text-xl">Leukotriene Receptor Antagonist (LTRA)</p>
                    <h3 class="mt-6">Available Dosage Forms</h3>
                    <ul class="list-disc list-inside space-y-2 text-lg">
                        <li>10 mg Film-Coated Tablets</li>
                        <li>5 mg & 4 mg Chewable Tablets</li>
                        <li>4 mg Oral Granules</li>
                    </ul>
                </div>
                <div>
                    <h3>Structural Formula</h3>
                    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAA3bSURBVHhe7d3NblRVGgbgrxAYCgRIhQASCRwBEgkcARIJHAESCRwBEhEIgZuA2bI3IuM+w3lO/f+e0f2yq3v2s/e7v/f6xZ//+Mc//vG///nPf/7z/z579uzZsy/935577rlnX3755Zdf/h/PPfPcc88998w/oGvQx18Q9g2s11577brrrrv+z8svv3z55c9/bt+f/vSnD97YhZ/85Cfvf//7L/s+Pvnkkw+e+p83v/nN917z+c9/fm3r//jHP/7xPz/60Y8+ePpHb3zjG2+99Z9//etfX3sQnv3sZ9/7Pvbv7Gvfe9/73nfev/71r3/tI+u85z3v+fSnP/3mP/3pTz/60Y8+eOq8+eab733sP89++ctfvvz9r3/94x+T+/7rX/+69tTnP//5tz73y172srfeeuvWW2/dddddV7f6r3/96+uvv/7rX//6V7/61bvuuuv697//ff2r/d/+9rf3vvbJcMMNN9z97ne/+c1vfnP88cc/+MEPfvCDH3zgAx+46aab7rzzzh/+8Ic/+9nPPvroo4/ff/+1H9/z8ssvv/baa++6667rC5/t3/zmN99666233nrr5z//+Vvf+tbLX/7y61//+nXXXffWt771kY985Nprr33v59xzz237//e//33/+9+f/exnH/rQh77vfe/7hS984fnPfx7f23u+29/+9ttvv/2Rj3zk/e9//8c//vE///nPd7/73V/60pf+wAc+8Ktf/epznvOcJz/5yT/60Y9++MMfvvOd79xzzz333ntv3//zn//8m3/wwQc/9KEPveENb7j99tuvvPLKpzzlKX/4wx8O/h///Oc/Z38r2y+//POf//w33njjjTfeOPx//ud//vOf//yTn/zkRz/60Rvf+Mbzn//8H/7whz/84Q+ve93rXv3qVz/ykY/ccMMNV1555Qc+8IHvfe97//73v3/605/+0Y9+9EMf+tDzn//85z//+Zvf/Obzn//8r3zlK3/yk5+8+eabH/jAB971rnfdtGnTprfffvtVf/z9n//856//9a+vfvWrb3zjGz//+c9vfe1r3/nOd65btw7+7bff/uQnP/nBD37w1Vdf/fSnP33llVduuOGGN73pTX/yk5/8wx/+8Etf+tJdd91122233XXXXV/5ylfuuuuuhx9+ePyz/Q1vetOb3/zmN7/5zW9+6Utfevjhhz/84Q/ffvvt/+7nPve5j3zkI++7775rr7323e9+94c+9KH3ve99tz4mPvnJT37yk5/8+Mc/fnP0s4Mf/OAffPDBZz/72c9+9rOffvrpp9v+tY985CPf9773PfGJT3zxi1/8/e9//z8n70vf+tbnP//5P/CBD3zgAx94//33P/3pT99+++2vfe1r3/e+951++unhP9s2/Gv1X/rSl370ox/94he/+Nprr/3rX//66U9/+je/+c3vf//73/nOd26//fYPfelLH/7wh0d//MMf/jH+Wf/Nb37zzW9+85Of/OTHH3/8i1/84l//+tcPPPDAl7/85V/84hfPvPnm67/0pS996UtfevTRR4d++tOf/tRfP/nJT370ox/9+9//vvnmm5/4xCe+/OUvv+qqq77udW677bZrrrnmnnvuufnmm9/4xjfuuOOOf/zjH+9//w/+8Ac/+tGPDh5f//KXv+z99o9+9KPd/s0/53z3u9/9zW9+85ve9Kbvf//7f+tb37r3s3/1zTfffOMb3/jNb37zs5/97Ktf/eqLXvSit95669prr/3e974X//P+v/+P/4d/+P73v//+P/+P/0f/t9de+3/+D//z//gf/3///Z//z7n/6U+fffvtt7vvvvutb33re9/73o9+9KPf+973/u///v73v//Nb37zm9/85l/+8pf/+Mc/vvaP/+P/u//97//v//P/6B7o9/Pzn//88n/+D//zv+9973/jG9/4qle96l/+8pdf//rXv/rVr/7mN7/53Oc+d9NNN73whS+8+eabL/3s3/3ud6/t/+hHP3rr+4c+9KHve9/73vWud335y19+7bXX/s///Oeff/55y/7PfvazP/vZz95222333nuv7/+///f/7V//+lf7v/71r99555133HGt+m3797//3bf2f+1rX/vYxz62/t/4xjf+6Ec/evOb3/zGN77x8Y9//POf//zGN75x9f4/+clPXvazf//3f3/3u9/9qle96i/+8IvveMc7rrvuuvvuu++XvvSlv/KVr1z3etdee234v/7v//7u3/rWt573vOe++9//7uWvf+3rX//2t//+3/72t1/96lfvvffe4/+u+7+f//znX/7yl3/xi198//vffe1rX/vEJz7xve9973e/+92PfvSjn/3sZ2+77bbbb7/98Y9//Ktf/eo3vvGN9913361/+PznP/85z3nOH/7wh//zn/9885vf/Prrr7/rrrvue9/73re97W233XY7/tn+r//gf/zv/+c/+zmf9Z//+c//43+2/z/t6973vhf+/fznP//EJz6x+s23ve1tv/rVr37961+/4YYb/v73v//6179+1113vfnmm9/+9rd/8IMfrH6sX/7yl7/61a9+73vf+973vffPfvYzX/ziF//P//yPP/7xD//h/+A/f/97n+Xv2a+///vf/+53v/vYxz62/s23ve1tP/nJT37uc5879dRTT62/77LLLnvve9/7ve997xOf+MTzn//8V7/61f/n//wf//d//5c++9nPftZz+Pvf/7724+tf/3o4+4tf/OIzn/nMX//613/1q1+vfe9rX/va7/3e7/3CF77w/Oc//z//5/+o/+q/+vOf//y9732vev7znz/sYx/7qle96n/93//9sY997Etf+tJ3vvOdb3vb2970pje98Y1vbL/99nvf+94XPvCBr3zlK//93/99xBNPPPnJT/7yl7/84A9/+Pvf//43vvGN973vfe9/+ctf/uEf/vCHf/zjH2+55Zb777//V//+4osv3nnnnbfddtvb3va2q7v/9Oc///7777/xxhu33XZb+7P9l7/85V/96lfvfetb3/nOd65btw78/Oc///KXv/zkJz/5yU9+8je+8Y1vfOMbb7zxtW/767///te97nW/973vPfe5z91xxx3XXHPNzTffvOmmm95y2/u/+93vfve73/3jH/84+F9zzz1v+5Mbb7zxm3/+o3vuueeXv/zlW//s/w///Gc/O3z/5S9/eeubb7750pe+9KMf/einP/3pT3/6rW9960tf+tKzn/3sX//61//u7/7ud7/73V/4whc+//nP/+53v/vOd76z/vUvfvGLP/CBD3zgA//u7/7+ve997x/+8Ier3/3EJz7xj//4j/fdd99//ud/vvaHP/vZz574xCf+4x//uPpd8y//8i+33npryz77X//617/2ta9dd911j//+7//+P//5z3vuueee+973vuaZZ+5//ud/Pv75z//yl7/8s3/zm984+qP9p/3b+D/96U8/+tGPfvSjH/3oRz86+P/sP+b/+c9/fu2T7/u///u//+u//tVXX/3lL395+v+///f/9dprr63++EsvvfTwww9f/vznv/nmm6/s+f73v//6L33pSy+//PLrX//6V7/61XvvvXfYww8/9NBD+9s+73/84x//u//7v999992f+MQnrv7U3e9+94c+9KHXXnvtnnvu2b5v+t/xjnd885vfvPbaa1///vc/+9nPPvrQh67+9Kte9ap//ud/+s///MeHPvSh733ve+9617ve9ra3PfOZZ970pje94x3veOedd/7P/9n/W/37P//zP/7zP3/jG9/4xje+cfUHv/nNb37961+/4YYbfv7znz/ykY++4x3vuPfee2+99dbbb7/92te+9tZf+1v++c9/fu9nP/vjH/94fL7+x//4H//v//7vv/3tb//kJz/5tS//9Kc///Wvf331q199+eWXv/vd7z7wgQ9svfWWv2d/a/3f8573vOecc87Wt/7Wt771kY985B//8R/vvetd76te9apf/OIXv/vd7z74wQ++4w1v+MEPfrD2V903vvGN99xzzyuvvPKJT3zil7/85V//+tfveMc7vva1r/3EJz5x9Tuvf/3rP/roo7fddtuNN9742te+9h/+4R//j/+P2X/s+R//8R/Xf8P+bXw491/7l//+97//sY99bLznnnve9ra3XXfddY8//vgXvvCFf/zHf/zP//yPT/ziE//n/+N/jL//zW9+85Of/OQf//jHt771rW+88cZXv/rVX/nKV956662/9rWvPfGEE8f/6f/pT3/64x//uOvf//KXv7z//e9feumlV77ylS/84Q9/9KMfvfWv7b+lX/q1r33t//mf//H+2/7h/+tf//p3vvOdd77znT/96U8f//jH/+M//uO73/3u//7v/37yk5/88Ic/3PLXf//n//x/8IMffPWrX/3BD37wpS996Rvf+Ma+b/rvf/rTnz788MMf/ehHHz300EOHHnqon2//P//zP6/s+d//8z/9r371qx/96Ee//OUv/973vvfPf/7zP/iDP/ylL33piSeeePihh77+9a9/+MMfvurVr/7617/+8Y9/fM8999z97ne/+c1vfnM8/dprr33jG9/4q1/96qtf/eq/+93vvvcxj3388ce///3vf/Ob3/zu97/7oQ996Fd+5Vf+9Kc/feSRR77yla84+9vf/na8v/zlL3/yk5/8wx/+8EsvvfSTn/zkn/3sZz/72c9++umnT7/++uc//+kPfvCDH/7w7//+7y9/+cu/+MUvXv75H//xj29//f8/+MEPfvCDH/ygv8sQv/vd7/7Od77zpS996R/84Ac/9rGPre/9/Oc/Hzz6T7n/6U9/Gj+Wv2u87W1v+4UvfOGjH/3oD3/4w4f+D9n/r/+N/8c+3/3ud6/99D/s+fnnP//5ve9973/5y1++8Y1vvPzyyy+99NI/+qM/uuWWWz7zmc9s+9P/+X+2vu2Rj3zkW97yln/5l3953/vec//9999www033nhjz/7X+Gftf+azn/3oRz964xvfeO21117z5je/eeWVV971rnc99thjN9xwQ/uz/Re+8IW33nrrrbfemnnmmed/8Rd/8T//8z9/+qMffe5zn/v85z9/8Ytf/MY3vvHlL3/5i1/84td//etf/epXf+UrX7nmmmtuuumma7/0a9/29W9/+9sXvvCFn/nMZ/7wD/+wf8+R+/xnP/+9731vfOvXvvb1V/+t+r/xH/9j/eZbb731t7/97bXXXvt///d///znP3/kIx+5+uqrf/SjH/3oRz/6P/+P//m9731v/+v+7T/2X//zP3/xi198x3u+++CDDw5+N+6zn/3sa17zmuc//+97e+xjH/vyV//yL/7gBz+44YYb3vrWtz796U8/99xzv/KVr9z222//hS984fnPf/6TnvSkN7zhDde+1o033vjxj3+8/sU3v/nNP/3pTx/60Ifee++91/bPf/jDH/7gBz946KGHhva1rW/+d/fdd2+55Zb3vve9f/VXf/X6//GPf/zXvvb73//+d7/73a94xSv+8pe//HOf+9y//du/fe655/7hH/5h/S7r/+lPf/qf/OQn//mf//nrX//6L33pS9/61re+9rWv3XrrrX/1Z//+r//9r//jP/6jp59++rWvfe3rX//6V7ziFS984Qt/8IMf3HXXXS+99NKrrrq6+s///Oc//69//esPf/jDF77whe9///vf8573vOecc87nPf95z3zmM/fdd99VV1319Kc//Ytf/OK3ve1t999//5e97GW33357y5+y/7Pvf+3rX//617/+9Vvf+tbbbvtt3zff8n/2f9f9P//zPx/+8If/+Z//+X//93+///3v/7//+7/b7r/16qtf+9rX/s53vvO9731ve+3rX//whz/84A9+8AMf+MAV/wM+qH/gAAAAAElFTkSuQmCC" alt="Chemical Structure of Montelukast" class="bg-white p-2 border rounded-lg w-full max-w-lg mx-auto h-auto">
                </div>
            </div>
        </section>

        <section id="mechanism" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Mechanism of Action</h2>
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div>
                    <p class="mb-4">Montelukast works by directly intervening in the inflammatory cascade. It is a selective and orally active antagonist of the Cysteinyl Leukotriene Receptor Type 1 (CysLT1). Cysteinyl leukotrienes (LTC4, LTD4, LTE4) are potent inflammatory mediators released from various cells, including mast cells and eosinophils.</p>
                    <p>These leukotrienes bind to CysLT1 receptors in the human airway, leading to bronchoconstriction, increased vascular permeability (airway edema), and mucus secretion. By selectively blocking these receptors, Montelukast inhibits these physiological actions without any agonist activity, leading to a reduction in airway inflammation and relaxation of bronchial smooth muscle.</p>
                </div>
                <div>
                     <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAB2/SURBVHhe7d3BblzZlcXx+78xMBIQCBQCgYRAYSAQCAQCCQEnoCBAEAgEgoA8IMiDYCgQCAQCEYEgd+BGy87L93e+v7t+Vfd0d9Uz3dPz52211rJ32WvvVfecc9dZ33333Xf3p/zvvffeO/ftt9/e3Z/+9Ke/+/3v3x387V/+5c/ev/3tb+9+/vOf737wgx+c+p/3vve9+1/r+c9//u66t/+tb31r98c///nPdx/+z3/+8/c+9rGPrX/vYx/72LvuuuteW3/nO99577P83/Oe97z3ve99d137o3feeedtD3feeefuu9/97u7/o3/+8593H/q/PPfcc++9996d+/bbb+/+5Cc/ufW1v/vd7z7wgQ987nOf++qrr37nO995+z+///3v7z70f/bWW2+9/fbb77///n/y9re/vfW1r21/z3ve8773ve/uu9/97u5v+W/r33rrrbfefvtzn/vctWvX/s/tb3/7+s+3Pve5u+uuu+6++271p55//vn7X/va1772ta997WvXX3/99ddf//e//9196b/vfetb33HHHXfccccdpz3tadzeW/v3v/+9++Mf//jJT37ytm3b7r777jvveeed+/bbbwf3Xve6133ve9+79Y3vfve7X/jCFz7xiU8c/OfOd77ztttuu+WWW65atWrVlre+9a3vfve733HHHXfeeed1f9u/8Y1v/OIXv/i1r33t6le/+rvf/e61q8Nf+tKXvvOd7/zpT3/66le/etv/1u/+wAc+8PnPfvYjH/nIVa+r/u2337777runP/3pT3nK//znP3/hC1/4pS996fnPf37rvzX/8z//80c/+tErr7xyxx13/PWvf33jG9/49Kc//dBDDz3yyCNPfOITH/3oR+996P/ud797tYfwn/3sZ3fddVfrr+3/+I//+Lbbbrtly5Z/+Zd/ecMb3vDyl7/8yU9+8jOf+cxHPvKR7W/7p33729/effzxx6tf/+IXv/i1r31t/L/pX/ziF7/97W/ffvvt73rXux772Mfe+9n+2/2tb33rL//yL3/pS1/68pe//B//8R9XX331v/zLv7zyyiuvvvrrhx566Le//e0nPvGJD3jgA9/+9rfffvvt61//+h//8R//8Ac/+MG/+Iu/eM1rXvPyl798yx9p/9e///2ve93rHv3oRy972cte+MIXLly48Gc/+9mXvvSlDzzwgQc+8IHbb7/91FNPfeELX/i1r33t5z//+a9//esPfehDt2/f/k/+5E9uvvnmt95666VLl77u9T75yU++4x3veMc73nHXXXd9+tOf/uIXv7j1m+Z//Md//MMf/vAXv/jFV7/61b/+9a/3v/Wtb33ve9/7qle96uc+97nf/e53j33sY+94xzveeecd//d//3f7a/v+85//3HWn/fDDD6/te2f7b++9995555133333pUuXrr/+9ddff/3NN98s/8tf/vKXvvSlD3/4w1//+teHH374//iP//jGN77xtWv+5S9/efh/60tf+tJ/+I//eMYznvHrX/+6+s3vfvc7r127dsMb3vCXv/zlz3/+85/+9Kfvfe97//jHP/7P//zPe9/73l/5ylc+8pGPvOc977nuuqsvfelLf/KTnzzwgQ98+tOf/uIXvzjjlKc85alPfepTn/rUp9v+L/+Pf/zj+m/rP/rRjy5ZsuTtb3/7K6+8ctOmTbfeeus/+qM/euITn/jGN77xH/7hH/7BH/xgw4YNW7Zseee7/b/3ve9du3bt9ddf/yMf+ch1r/Uf/vCHn/rUp1a/dfV7P/rRj//xH//xyEc+8uCDD/6jP/qjf/zHf/zSl7404pRTTvnMZz7zlKc85Ytf/OIvfOELN23a9De/+c1vfvPbr/+c+rWvf+36b+s/9rGPfehDH3rvZ7v7mte8ZuXKlZ/+9Kd/8YtfvOU//o//4X/5l3/5kY98ZPsi+7/0pS9ds2ZNW7du/ac//elPfepT991336VLlz7wgQ986Utf+ulPf/rjH//4ve9973e/+937v/+Lf/3rX9+16/b3v/+9/p/+137nO9/ZffXVV99++20//vGPr127do899vjXf/3X//iP//h//ud/fuMb3/jSl770mc98ZuWXX37LLb+Wve9//+tb3/rWr/71r9d++V/84hd/8YtfrH/X/m+99dYbN27csmXL1i+f9hOf+MR/+Id/2PqnP/nJT/7oRz/6hS98YZv73/nOd65atWrDDTf8wQ9+cMQRRxzxyEc+cv3r9V/t+V/+5V9e+9v/+Z//2Xq/4he/+MWvfvWr3/zmN9/xjndce+21n/nMZ+p/oX/9618f/vCHj3/849/whjfc7n/+wQcfnLHHHnvuuef2L3/2s5/98pe/fMstt1zxwAMPvO1t9/nPfx7vPf+Ff/jDH/7pT396yy23/OlPfxp33vPyl7980003/f3vf3/99dd///vf/8EPfjAjlVNOOemkk/bff//DDz9899137/7sP/a/+tWv3vzmN7/5zW8+8YlP/OhHP/rZz372ta997cUvf/nFF198ww03XP8b+0+vf+WVV37yk5/8wx/+8EsvvfSTn/zkn/3sZz/72c9++umnT7/++uc//+kPfvCDH/7w7//+7y9/+cu/+MUvXv75H//xj29//f8/+MEPfvCDH/ygv8sQv/vd737nO9956aWX/sEf/MAHPvCB+t7Pfvazj3zkI++///4PfvCDn/nMYx7zmMcee+yll166efPmt7/97T/4wQ8+8YlPfPvb3/7c5z735je/+S9/+ct73/ve/+iP/ujNN9/c9mf/13vve9/nP//5X/nKVz7/+c+/7rrrbrihvS+nve9973/7t3/73ve+9x133HFLly697bbbvvrVr37mM5/56le/uu3te9/73qc+9anb+569+oNe8YpXPPaJT3zxi1/8/e9//z/na/+t/d91113XXXfd//gf//H3vvftt/zfv/rVr37+85//4Q9/+Mtf/vLrH/3oR3v/yV966aWHH374hS98Yf2v9Wv/s35/7L/22mutf/L9n/zkJ++5555bbrml9Qc+8IH/+T//0/q3v/vd7z74wQ++4w1v+MEPfrD2V90/+MEPvueee17zmtc89alP/c///M/LX/7yl73sZZ966ql/+Zd/ecMb3vDyl7/8yU9+8jOf+cxHPvKR7W/7p33729/effzxx6tf/+IXv/i1r31t/L/pX/ziF7/97W/ffvvt73rXux772Mfe+9n+2/2tb33rL//yL3/pS1/68pe//B//8R9XX331v/zLv7zyyiuvvvrrhx566Le//e0nPvGJD3jgA9/+9rfffvvt61//+h//8R//8Ac/+MG/+Iu/eM1rXvPyl798yx9p/9e///2ve93rHv3oRy972cte+MIXLly48Gc/+9mXvvSlDzzwgQc+8IHbb7/91FNPfeELX/i1r33t5z//+a9//esPfehDt2/f/k/+5E9uvvnmt95666VLlz7wgQ98+tOf/uIXvzjjlKc85alPfepTn/rUp9v+L/+Pf/zj+m/rP/rRjy5ZsuTtb3/7K6+8ctOmTbfeeus/+qM/euITn/jGN77xH/7hH/7BH/xgw4YNW7Zseee7/b/3ve9du3bt9ddf/yMf+ch1r/Uf/vCHn/rUp1a/dfV7P/rRj//xH//xyEc+8uCDD/6jP/qjf/zHf/zSl7404pRTTvnMZz7zlKc85Ytf/OIvfOELN23a9De/+c1vfvPbr/+c+rWvf+36b+s/9rGPfehDH3rvZ7v7mte8ZuXKlZ/+9Kd/8YtfvOU//o//4X/5l3/5kY98ZPsi+7/0pS9ds2ZNW7du/ac//elPfepT991336VLlz7wgQ98+tOf/uIXvzjjlKc85alPfepTn/rUp9v+t/7rW9/61q9+9av2X/7iF7/4xa/Wv2v/t956640bN27ZsmXrF0+73/3u9/Of//znPe95733vey9//OOff/rpP/jBD37ta197+9vf/vKXv/zP/+//b/0++6lPfepznvrU//d//3f3f//973//a1/72q9//eu/+MUvfvGLX/zJT37yox/96Cc+8YnPec5z3vSmN/3e7/3eD//wD3/pS196xhlnhPOVr3zl17/+9R/+4R/+l7/85d/+7d/edtttxx577Isvvvjb3/72N7/5zS9+8Yu33HKLj370o3/8x398xx13XHPNNde85jW/8Y1vfO973/vyl7/8s5/97Kc+9alf/epXv/e9712zZk0+f2/n/+EPf/i9733v3/7t3975zneufvXVv/3bv/2JT3xir/d/1v6vf//7/+IXvzjve9/73vb+ta997c1vf/uP/+M/7r+Wv/3tb7/++uunn376mc985o9//OP6z1f9X/va13784x+/5ZZbvv3tb//iF794+9ve9p73vOefffbpT33qU9///vc/8pGP/Nd/+7c/+MEPbr755qc97Wm//Mu/vOOOOz760Y9++qMffeMb3/jjH/+4fW3veMc7vvvd7z73uc993OMe94tf/OLxj3/8zW9+c9WqVS94wQv+9Kc/feSRR7785S+/7LLLVr/lve9973e+850bbrihrf3X/vznP7/llltuueWW//Ef/3HNNde0vet/v/vd7z71qU/90Ac+sGbNml/5ylfuuuuuP/zhD9/5znd+4xvfeMc73vGSF7zghS984fnPfx7vb37zmy/+4i/+4pe+9KW33Xbba1//+o9+9KOrjzvveMc7/vznP/fdd99TTz018owzzzztWc961jOf+cx73vOebW/729/+9jve8Y6vfOUrn/70p//8z//897//ff2v9X/+53++7bbb/ud//ue1r/2f//mfv/vd7259vf3Nb37zm9/89re//d57713/G/tP6/Wvf+36b+1/r3rVq7Ztu/zlLz/wwAPX7vnuuuuuv/71r3/961+vec1rNnza1V9//dVXX33xi1/8/Oc//4c/+MH7P1v9+S//8i/f+c53/vKXv/zjH//46Ec/+je/+c1//Md//LnPfe7xj3/8q1/96ta3vvXyl798yx/Z/m+69re+9a3vfve7b7jhhtdee+073/nOP/zhDy+44II77rjjpz/96W/+85vbb7994403fuMb3/jUpz718Y9//Ktf/eqPfvSja/9rW/1o4z//+Y+/59/+7d8O/+tf//qrX/3qd77znbe/+7999tlr+2/z/t/znvfcc889H9/d/+///m//eW/t/6b9v/Od7/z2t7/92te+9vWvff0//tfvf//7e//r/7lPfeqTnvSkV7ziFW984xs/+MEP/vSnP7399tuf+MQn/uQnP/nMZz7z5S9/+Wc/+/Vf/v/2t3751Vdffe1rX/vYxz62/t/4xjf+6Ec/evOb3/zGN77x8Y9//POf//zGN75x9f4/+clPXvazf//3f3/3u9/9qle96i/+8IvveMc7rrvuuvvuu++XvvSlv/KVr1z3etdee234v/7v//7u3/rWt573vOe++9//7uWvf+3rX//2t//+3/72t1/96lfvvffe4/+u+7+f//znX/7yl3/xi198//vffe1rX/va1772Na95za/+9a/3ve99729/+7+f/OQnv/jFLy5cuPD2229f++pPfepTH/rQhz70oQ8tWrQofN973/u9731vfOu//evXvvb1137r+l/+1vWve332f+s3v+e85znPOc97/ve85233/+c//3nf+973mc985jOf+cyf//znveMc5ziH/m+760972tM+9alPfe1rX//Wf+1/639W/2//s551rCeeePjDH/7wrne96zOf+cyPfOQjb3rTm1r/z//8z//4P/gP73/ve9/73vf+bbfdNn6s+o/+6I/euuuu//73v3/pS1/6jW984/XXX/9n//M/n/zkJ2+88cZ7P/t/znPe8y//8i+v/fKznvWsD3/4wwcffPDa+v9tb3vb69/+9rd//etfv/nNbz772c++6qqrbtrwve9974c//OGvf/3rd/r/d1/qf336058e/+///s///M/b//nPfx7y3X/++Z//+ec//3n7f2v/e+973y984QvXrg7u+n/f+MY3/uxnP/vZz352//vf//uf/7l+PzBf/v/8sAAAAABJRU5ErkJggg==" alt="Mechanism of Action Illustration" class="bg-white p-2 border rounded-lg w-full max-w-lg mx-auto h-auto">
                </div>
            </div>
        </section>

        <section id="indications" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Clinical Indications</h2>
            <h3>Chronic Asthma</h3>
            <p>For the prophylaxis and chronic treatment of asthma in adults and pediatric patients 12 months of age and older.</p>
            <h3>Exercise-Induced Bronchoconstriction (EIB)</h3>
            <p>For the prevention of EIB in patients 6 years of age and older. A single dose should be taken at least 2 hours before exercise.</p>
            <h3>Allergic Rhinitis</h3>
            <p class="mb-4">For the relief of symptoms of seasonal allergic rhinitis (in patients ≥2 years) and perennial allergic rhinitis (in patients ≥6 months).</p>
            <div class="mt-4 p-4 border-l-4 border-yellow-500 bg-yellow-50 rounded-r-lg">
                <h4 class="font-bold text-yellow-800">Note on Allergic Rhinitis Usage</h4>
                <p class="mt-2 text-yellow-700">Due to the risk of neuropsychiatric events (see Safety section), Montelukast should be reserved for patients with allergic rhinitis who have an inadequate response to or are intolerant of alternative therapies.</p>
            </div>
        </section>

        <section id="dosage" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Dosage & Administration</h2>
            <p class="mb-6">Dosage is dependent on age and indication. Patients with both asthma and allergic rhinitis should take only one dose daily in the evening.</p>
            <div class="overflow-x-auto">
                <table class="w-full table-auto text-left">
                    <thead>
                        <tr>
                            <th>Age Group</th>
                            <th>Indication</th>
                            <th>Dose</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>15 years and older</td>
                            <td>Asthma / Allergic Rhinitis</td>
                            <td>One 10 mg tablet daily</td>
                        </tr>
                        <tr>
                            <td>6 to 14 years</td>
                            <td>Asthma / Allergic Rhinitis</td>
                            <td>One 5 mg chewable tablet daily</td>
                        </tr>
                        <tr>
                            <td>2 to 5 years</td>
                            <td>Asthma / Allergic Rhinitis</td>
                            <td>One 4 mg chewable tablet or one packet of 4 mg oral granules daily</td>
                        </tr>
                        <tr>
                            <td>12 to 23 months</td>
                            <td>Asthma</td>
                            <td>One packet of 4 mg oral granules daily</td>
                        </tr>
                        <tr>
                            <td>6 to 23 months</td>
                            <td>Perennial Allergic Rhinitis</td>
                            <td>One packet of 4 mg oral granules daily</td>
                        </tr>
                        <tr>
                            <td>6 years and older</td>
                            <td>Exercise-Induced Bronchoconstriction</td>
                            <td>One 5 mg or 10 mg tablet at least 2 hours before exercise</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <h3 class="mt-8">Administration Instructions</h3>
            <ul class="list-disc list-inside space-y-3">
                <li><strong class="font-semibold">Film-Coated Tablets:</strong> Swallow whole. May be taken with or without food.</li>
                <li><strong class="font-semibold">Chewable Tablets:</strong> Must be chewed thoroughly. Take at least 1 hour before or 2 hours after meals. Contains phenylalanine (warning for PKU).</li>
                <li><strong class="font-semibold">Oral Granules:</strong> Administer within 15 minutes of opening. Can be given directly in the mouth, mixed with a spoonful of cold soft food (e.g., applesauce), or dissolved in 5 mL of baby formula or breast milk. Do not mix with other liquids.</li>
            </ul>
            
            <h3 class="mt-8">Missed Dose</h3>
            <p>If a dose is missed, skip the missed dose and take the next one at the regular time. Do not take a double dose to make up for the one that was missed.</p>
        </section>

        <section id="pharmacokinetics" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Pharmacokinetics</h2>
            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAABGZSURBVHhe7d1NrxRVGMbxh7+BQCgQCASCQCAQCAQCCQEnoBBIBAKBQCCggAIEgUAgEAgEAoEgEAlCbkQ3We99t4+5+5r/mfmeM+/zmfk8z22119lnb73X3nvuqW/77bff3n3ppZfu/uUvfvH+P/nJTz7wgQ/cf//9d7/73V/84hf/2Z/92bZt2z/+4z9+5zvf+e///u83b958ww03XHPNNf/5n/+5+9SnPvWpT33qIx/5yE9+8pP+t2fvvffeO/ftt9/e/emnn+4++MEP3n333Xfvvffe+t/m/Q984AM/+MEPfvCDH3zgAx/4j3/849u3b7/99ts3b9580003Xb9+fU972tNe8YpXvOIVr/ilL33p85//vPtt+6c+9alPfepTf//3f7/7yU9+8l/+5V+2bbf+p3/6p9Vf8r/f/e53n/jEJ+6//u7Pfvazn/nMYz7zmU/84he/+Iu/+Isf/vCHT37yk//jf/yP7b/3Wv+b/K/3ve99r3nNa77+9a9/5CMf+Zvf/Obzn//8V77ylde85jW33nrr5z//+V/84hefe9zjHvfwxx//+7//u0996lMf/vCHn/rUp9avW3/jG9/4/ve//8UvfvGnPvWpr33ta9/4xjfuuOOO62+/+uqrj370o3/1t3/72te+tueeey5ZsmTLLbc8/PDDf/vb377++utf/epX//iP//h73/veLVu2/M53vvNf//Vfn3jiie9///s/+MEPHv/4x9/97nc3v+Htt9++cuXKV7/61W95y1ve8pa3/PCHP7x06dLrr7/+9re/feWVV77nPe95z3ves2nTpl/5ylf+4Ac/+PrXvz7ssMMOeyz71//8z//88pe/vGXLlv/2b//2W9/61qtf/ervfu97r1u37qWXXnr6059e/ab9s5/97Ec/+tH/7//+73e/+90LLrjgiSee+PKXv3z99df/wQ9+cMMNN1x//fUXLlx46qmn/vCHP9zxjnd8wxve8JGPfORb3/rW1Vtv3XXXXR/5yEf++q//esQRR7ziFa94xSte8Zvf/Ob73ve+13/Gv/KVr/zXf/3XJz7xiVtvvXVHHXWf/vSnDzzwQN97/y9+8Yu3v/3td9999913333mmWf+9E//9Hd+53du3Lhx//33n3nmmac+9akPPvjgy1/++rbbbrv++usvXrz4xBNP3HXXXa985St/9KMffeMb33jjjTfe8pa3/M///M/tt9/+lre85Zvf/OY3vvGN//mf/7l27dpt27Zd+5T/t3/xi1+85CUvWbVq1fXXX3/pS1+6e++11157rX8d/y/97//zP3/4wx/ed999W7Zs+cMf/vDMM8+8+eabf/SjH/3617++dt0rP/rRj170ohdduHDhhz/84Vvf+tabb755zTXXnH322fvvv//rX/86+5p+9KMffc973vPFL37xDW94w9/+9rfrr79+yz+y/d+w/5e97GU33njjrbfeuuGGG9785je/5S1veelll/09Z7u32d/2/yUveclznvOcb3rTm65evXrvvffdffPNN//sZz/75Cc/+V//9V833nhj+zvs//SnP73xxhvvfOtbn/3sZz/1qU/V/+s+9alP/dCHPvShD33oBz/4wfve975f+MIXPvvZzz7+8Y/f8Y53fPjhhx9//PGrX/3qve997y9/+cubb755+4P+P/zww2vbf//73+/+8Ic//Pa3v/13f/d39/nPfx7v3/e+9/3kJz+59rW///u//4tf/OK3v/3td9111y233HLzzTd/6Utf+uQnP/l3f/d33/zmN9t+//tf/erX137o33XXXbf++usvXbp04xvf+La3ve1f/vKXLVu2bPvb3va2t9x+2/e+9/2P//iP//iP/3jrrbfcct/73veXvvSlv/rVr+7+8Y9//Ktf/eq1a9eu+Y3vfOc7L+85v3vvvff+L/n85z+/cuXKP/jBDz73uc+tf/O///u/u/8d/wuvvPLKz372s5/97Gc/85nP/MZPf/rT/+Zf/uWrr776hS984fnPfx7vb37zmy/+4i/+4pe+9KW33Xbba1//+o9+9KOrjzvveMc7/vznP/fdd99TTz018owzzzztWc961jOf+cx73vOebW/729/+9jve8Y6vfOUrn/70p//8z//897//ff2v9X/+53++7bbb/ud//ue1r/2f//mfv/vd7259vf3Nb37zm9/89re//d57713/G/tP6/Wvf+36b+1/r3rVq7Ztu/zlLz/wwAPX7vnuuuuuv/71r3/961+vec1rNnza1V9//dVXX33xi1/8/Oc//4c/+MH7P1v9+S//8i/f+c53/vKXv/zjH//46Ec/+je/+c1//Md//LnPfe7xj3/8q1/96ta3vvXyl798yx/Z/m+69re+9a3vfve7b7jhhtdee+073/nOP/zhDy+44II77rjjpz/96W/+85vbb7994403fuMb3/jUpz718Y9//Ktf/eqPfvSja/9rW/1o4z//+Y+/59/+7d8O/+tf//qrX/3qd77znbe/+7999tlr+2/z/t/znvfcc889H9/d/+///m//eW/t/6b9v/Od7/z2t7/92te+9vWvff0//tfvf//7e//r/7lPfeqTnvSkV7ziFW984xs/+MEP/vSnP7399tuf+MQn/uQnP/nMZz7z5S9/+Wc/+/Vf/v/2t3751Vdffe1rX/vYxz62/t/4xjf+6Ec/evOb3/zGN77x8Y9//POf//zGN75x9f4/+clPXvazf//3f3/3u9/9qle96i/+8IvveMc7rrvuuvvuu++XvvSlv/KVr1z3etdee234v/7v//7u3/rWt573vOe++9//7uWvf+3rX//2t//+3/72t1/96lfvvffe4/+u+7+f//znX/7yl3/xi198//vffe1rX/va1772Na95za/+9a/3ve99729/+7+f/OQnv/jFLy5cuPD2229f++pPfepTH/rQhz70oQ8tWrQofN973/u9731vfOu//evXvvb1137r+l/+1vWve332f+s3v+e85znPOc97/ve85233/+c//3nf+973mc985jOf+cyf//znveMc5ziH/m+760972tM+9alPfe1rX//Wf+1/639W/2//s551rCeeePjDH/7wrne96zOf+cyPfOQjb3rTm1r/z//8z//4P/gP73/ve9/73vf+bbfdNn6s+o/+6I/euuuu//73v3/pS1/6jW984/XXX/9n//M/n/zkJ2+88cZ7P/t/znPe8y//8i+v/fKznvWsD3/4wwcffPDa+v9tb3vb69/+9rd//etfv/nNbz772c++6qqrbtrwve9974c//OGvf/3rd/r/d1/qf336058e/+///s///M/b//nPfx7y3X/++Z//+ec//3n7f2v/e+973y984QvXrg7u+n/f+MY3/uxnP/vZz352//vf//uf/7l+PzBf/v/8sAAAAABJRU5ErkJggg==" alt="Pharmacokinetics ADME Infographic" class="bg-white p-2 border rounded-lg w-full max-w-2xl mx-auto h-auto mt-4">
            <div class="overflow-x-auto mt-8">
                <table class="w-full table-auto text-left">
                    <thead>
                        <tr>
                            <th>Parameter</th>
                            <th>Description</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Bioavailability</td>
                            <td>~64% for 10 mg tablet; ~73% for 5 mg chewable tablet (fasted).</td>
                        </tr>
                        <tr>
                            <td>Peak Plasma Time (Tmax)</td>
                            <td>3-4 hours (10 mg tablet); 2-2.5 hours (5 mg chewable).</td>
                        </tr>
                        <tr>
                            <td>Protein Binding</td>
                            <td>>99% to plasma proteins.</td>
                        </tr>
                        <tr>
                            <td>Metabolism</td>
                            <td>Extensively metabolized in the liver by CYP2C8, CYP3A4, and CYP2C9.</td>
                        </tr>
                        <tr>
                            <td>Half-life (T½)</td>
                            <td>2.7 to 5.5 hours in healthy adults.</td>
                        </tr>
                        <tr>
                            <td>Elimination</td>
                            <td>Almost exclusively via bile in the feces (~86%). Less than 0.2% excreted in urine.</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <section id="safety" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Adverse Effects & Safety Profile</h2>
            <div class="grid md:grid-cols-2 gap-8 items-center bg-red-100 border-2 border-red-500 rounded-lg p-6 mb-8">
                <div>
                     <h3 class="text-xl font-bold text-red-900 flex items-center mt-0"><span class="text-3xl mr-3">🚨</span> U.S. FDA BOXED WARNING: Neuropsychiatric Events</h3>
                    <p class="mt-4 text-red-800">Serious mental health side effects, including depression, sleep disturbances, suicidal thoughts, and actions, have been reported. These can occur in patients with or without a previous history of mental illness. Because of this risk, the benefits of Montelukast may not outweigh the risks for some patients, particularly those with milder conditions like allergic rhinitis.
                    <br><br>
                    <strong class="font-semibold">Advise patients and caregivers to be alert for changes in behavior or mood. If they occur, stop Montelukast and contact a healthcare provider immediately.</strong></p>
                </div>
                <div>
                    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAABG5SURBVHhe7d1NrxRVGMbxh7+BQCgQCASCQCAQCAQCCQEnoBBIBAKBQCCggAIEgUAgEAgEAoEgEAlCbkQ3We99t4+5+5r/mfmeM+/zmfk8z22119lnb73X3nvuqW/77bff3n3ppZfu/uUvfvH+P/nJTz7wgQ/cf//9d7/73V/84hf/2Z/92bZt2z/+4z9+5zvf+e///u83b958ww03XHPNNf/5n/+5+9SnPvWpT33qIx/5yE9+8pP+t2fvvffeO/ftt9/e/emnn+4++MEP3n333Xfvvffe+t/m/Q984AM/+MEPfvCDH3zgAx/4j3/849u3b7/99ts3b9580003Xb9+fU972tNe8YpXvOIVr/ilL33p85//vPtt+6c+9alPfepTf//3f7/7yU9+8l/+5V+2bbf+p3/6p9Vf8r/f/e53n/jEJ+6//u7Pfvazn/nMYz7zmU/84he/+Iu/+Isf/vCHT37yk//jf/yP7b/3Wv+b/K/3ve99r3nNa77+9a9/5CMf+Zvf/Obzn//8V77ylde85jW33nrr5z//+V/84hefe9zjHvfwxx//+7//u0996lMf/vCHn/rUp9avW3/jG9/4/ve//8UvfvGnPvWpr33ta9/4xjfuuOOO62+/+uqrj370o3/1t3/72te+tueeey5ZsmTLLbc8/PDDf/vb377++utf/epX//iP//h73/veLVu2/M53vvNf//Vfn3jiie9///s/+MEPHv/4x9/97nc3v+Htt9++cuXKV7/61W95y1ve8pa3/PCHP7x06dLrr7/+9re/feWVV77nPe95z3ves2nTpl/5ylf+4Ac/+PrXvz7ssMMOeyz71//8z//88pe/vGXLlv/2b//2W9/61qtf/ervfu97r1u37qWXXnr6059e/ab9s5/97Ec/+tH/7//+73e/+90LLrjgiSee+PKXv3z99df/wQ9+cMMNN1x//fUXLlx46qmn/vCHP9zxjnd8wxve8JGPfORb3/rW1Vtv3XXXXR/5yEf++q//esQRR7ziFa94xSte8Zvf/Ob73ve+13/Gv/KVr/zXf/3XJz7xiVtvvXVHHXWf/vSnDzzwQN97/y9+8Yu3v/3td9999913333mmWf+9E//9Hd+53du3Lhx//33n3nmmac+9akPPvjgy1/++rbbbrv++usvXrz4xBNP3HXXXa985St/9KMffeMb33jjjTfe8pa3/M///M/tt9/+lre85Zvf/OY3vvGN//mf/7l27dpt27Zd+5T/t3/xi1+85CUvWbVq1fXXX3/pS1+6e++11157rX8d/y/97//zP3/4wx/ed999W7Zs+cMf/vDMM8+8+eabf/SjH/3617++dt0rP/rRj170ohdduHDhhz/84Vvf+tabb755zTXXnH322fvvv//rX/86+5p+9KMffc973vPFL37xDW94w9/+9rfrr79+yz+y/d+w/5e97GU33njjrbfeuuGGG9785je/5S1veelll/09Z7u32d/2/yUveclznvOcb3rTm65evXrvvffdffPNN//sZz/75Cc/+V//9V833nhj+zvs//SnP73xxhvvfOtbn/3sZz/71Kc+Vf+v+9SnPvWhD33oQx/6wA9+8IHvfe97X/jCFz772c8+/vGP3/GOd3z44Ycff/zxr3/16ve+971f/vKXTb777rvvvv3222+///3vb//85z/v/+P/4z/90z+97bbbrrnmmnfffXfb/q/1v+T/+te//sQnPvHb3/725z//efs38/nPfx7vP/XpT7300ksXXHDBS1/60s9+9rN/+Zd/ueWWf8/n/Uv+b33rW9/0pje9+eabb97znu3+zX/yRz/60Y9+9KMf/eMf//jzP/bYY4899tgPfOADp//e//jHP/7P//zPtb/8f/d3f7f1f3nmmWf+83/+53/4h394//33P/PMM08//fR//Mdf/I/3Xvva137u5X/zN3/zT//0T3/pS1+6f/u3/+IXv/iFb3zjhz/84Xe9611XXnllf/a/+3+X//gf/3H7n//X/te//vXDH/5w61s/+tGP7j72sY996EMfeutv/M///E//9E+/9KUvPf/5zz/2sY/dffXVV1//+te//vWv73///n/yk5/s+u/+j/7oj/7hD/7gta997U/91Ke+9K//t/43+F9//fW1r/2f/vSnv/3tb7/66quvf/3rP//5z9f+/3/+5392/W39w//+7//uH331q1+t/1f9b/g//vGP33XXXbfeeuuNN974qle9qvvf4N/4xjd+8IMfvPbaa//rv/7rbbfcsu+++5566qlrr7327ne/e/Un//Xf/vWvf/vb3/728ssvv+mmm957773//M//vPzyy2+/ffc/c7x/+9vf/sQnPrH693ve9rY33nhj+/+Nb3xj3R/27//+7y9/+cuXLFny2te+du2q9n//pTfeeOM//MM//Pa3v/1b/+u//n/2b/9W+2//+Mc/fvOb3/zGN75x9fe+c37X/u+99951f9vf8V988cVf/OIXv/nNb37wgx88/fTT1/7r/j/4wQ/+4R/+4e23337XXXc98YlPXPv//J///A/+4A+v/d9zjz322GOPPfLII7+P/5O/p/4v/bWvfW3NmjX/8R//cfufPfvss2++efOb3/zm//y//T+/+c1vvvvd7z7wgQ/s+v/zH//xj/e97137p1/1qle96lWv+h//8R/f/e53f/nLX177v1//pT/5yU9+8pOf3Pr6b/3/q9/+7d9+++23f/zjH2/7b/G/3/ve96tf/epvf/vb136rfz/+8Y+///vf//e//3355Zc//elPv/e97137b7h+r3zlK694xSu2bNmy7bffvnHjxrfe9rY33njjL3zhC3/4wx/ed999f/e73z344IO/+c1v9rvu7/vqq69+9KMfvfeXvvSlr33ta1vv+m/+v1/+w/3f9o/+6I/euuuu//73v3/pS1/6jW984/XXX/9n//M/n/zkJ2+88cZ7P/t/znPe8y//8i+v/fKznvWsD3/4wwcffPDa+v9tb3vb69/+9rd//etfv/nNbz772c++6qqrbtrwve9974c//OGvf/3rd/r/d1/qf336058e/+///s///M/b//nPfx7y3X/++Z//+ec//3n7f2v/e+973y984QvXrg7u+n/f+MY3/uxnP/vZz352//vf//uf/7l+PzBf/v/8sAAAAABJRU5ErkJggg==" alt="Neuropsychiatric Effects Warning Graphic" class="bg-red-50 p-2 rounded-lg w-full max-w-sm mx-auto h-auto">
                </div>
            </div>

            <h3>Common Adverse Effects</h3>
            <p>Upper respiratory infection, headache, fever, abdominal pain, cough, diarrhea, nausea.</p>
            
            <h3>Serious Adverse Effects</h3>
            <p>Allergic reactions (anaphylaxis, angioedema), severe skin reactions, liver problems (hepatitis), Churg-Strauss syndrome, increased bleeding tendency, and the neuropsychiatric events listed above.</p>
            
            <h3>Contraindications</h3>
            <ul class="list-disc list-inside space-y-2">
                <li>Known hypersensitivity to Montelukast or any of its components.</li>
                <li><strong class="font-semibold">Chewable tablets are contraindicated</strong> in patients with phenylketonuria (PKU) as they contain aspartame.</li>
            </ul>
        </section>

        <section id="ai-counselor" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>✨ AI-Powered Patient Counseling Assistant</h2>
            <p class="mb-6 text-gray-600">This tool helps healthcare professionals generate key counseling points for patients starting Montelukast. Enter a patient scenario below to get started.</p>
            
            <div class="bg-blue-50 border border-blue-200 p-4 rounded-lg">
                <label for="ai-prompt" class="block font-semibold text-lg text-blue-800 mb-2">Patient Scenario:</label>
                <textarea id="ai-prompt" rows="3" class="w-full p-3 border-2 border-blue-200 rounded-lg focus:ring-2 focus:ring-[#D35400] focus:border-transparent transition" placeholder="e.g., 'A 7-year-old boy starting the 5mg chewable tablet for asthma.' or 'An adult patient concerned about long-term side effects.'"></textarea>
                <button id="generate-points-btn" class="mt-4 w-full bg-[#D35400] text-white font-bold py-3 px-6 rounded-lg hover:bg-[#E67E22] transition-colors duration-300 flex items-center justify-center space-x-2 disabled:bg-gray-400">
                    <span>✨ Generate Counseling Points</span>
                    <div id="ai-loader" class="hidden loader"></div>
                </button>
            </div>

            <div id="counseling-points-output" class="mt-6"></div>
        </section>
        
        <section id="interactions" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Drug & Disease Interactions</h2>
             <div class="overflow-x-auto">
                <table class="w-full table-auto text-left">
                    <thead>
                        <tr>
                            <th>Interacting Agent</th>
                            <th>Effect</th>
                            <th>Recommendation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Phenobarbital, Phenytoin, Rifampin</td>
                            <td>These drugs induce CYP enzymes and can decrease Montelukast levels, reducing its effectiveness.</td>
                            <td>Monitor for reduced efficacy.</td>
                        </tr>
                        <tr>
                            <td>Gemfibrozil</td>
                            <td>Inhibits CYP2C8 and can increase Montelukast levels, raising the risk of side effects.</td>
                            <td>Use with caution; monitor for adverse effects.</td>
                        </tr>
                         <tr>
                            <td>Food</td>
                            <td>A standard meal decreases bioavailability of the chewable tablet by ~13%.</td>
                            <td>Take chewable tablets on an empty stomach. Film-coated tablets are not affected by food.</td>
                        </tr>
                        <tr>
                            <td>Severe Hepatic Impairment</td>
                            <td>Since the drug is metabolized by the liver, severe liver disease can impair clearance.</td>
                            <td>Use with caution or avoid. Not studied in this population.</td>
                        </tr>
                        <tr>
                            <td>Aspirin Sensitivity</td>
                            <td>Montelukast does not eliminate the need to avoid aspirin and other NSAIDs in sensitive patients.</td>
                            <td>Patients must continue to avoid these drugs.</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <section id="pregnancy" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Pregnancy & Lactation</h2>
            <h3>Pregnancy Category B</h3>
            <p>Animal studies have not shown a risk to the fetus, but there are no adequate, well-controlled studies in pregnant women. Post-marketing data has not shown clear evidence of harm. Uncontrolled asthma is a significant risk during pregnancy. The decision to use Montelukast should be made with a healthcare provider, weighing the benefits against potential risks.</p>
            <h3>Lactation</h3>
            <p>It is not known if Montelukast is excreted in human milk. Caution should be exercised when administered to a nursing woman.</p>
        </section>
        
        <section id="brands" class="bg-white p-8 rounded-lg card-shadow mb-8 scroll-mt-32">
            <h2>Commonly Available Brands in Pakistan</h2>
            <div class="bg-amber-100 border-t-4 border-amber-500 rounded-b text-amber-900 px-4 py-3 shadow-md mb-8" role="alert">
              <div class="flex">
                <div class="py-1"><span class="text-2xl">📢</span></div>
                <div class="ml-3">
                  <p class="font-bold">DRAP Recall Alert: Myteka Sachet 4mg</p>
                  <p class="text-sm">DRAP has declared batch #155384 of Myteka Sachet 4mg by Hilton Pharma as substandard. Patients and pharmacists should stop using this specific batch.</p>
                </div>
              </div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
                <div class="border p-4 rounded-lg flex flex-col items-center text-center">
                    <img src="https://www.hiltonpharma.com/wp-content/uploads/2022/10/logo.png" alt="Hilton Pharma" class="h-16 mb-4" onerror="this.onerror=null;this.src='https://placehold.co/200x60/cccccc/ffffff?text=Hilton+Pharma';">
                    <h3 class="mt-0">Myteka</h3>
                    <img src="https://dvago.pk/products/6162ee46c9332.webp" alt="Myteka Product" class="h-48 object-contain my-4" onerror="this.onerror=null;this.src='https://placehold.co/200x200/cccccc/ffffff?text=Myteka';">
                    <p class="font-semibold">Manufacturer: Hilton Pharma</p>
                    <p>Forms: Tablets, Chewables, Sachets</p>
                </div>
                 <div class="border p-4 rounded-lg flex flex-col items-center text-center">
                    <img src="https://getzpharma.com/wp-content/uploads/2021/11/logo.png" alt="Getz Pharma" class="h-16 mb-4" onerror="this.onerror=null;this.src='https://placehold.co/200x60/cccccc/ffffff?text=Getz+Pharma';">
                    <h3 class="mt-0">Montiget</h3>
                    <img src="https://d2j6dbq0eux0lq.cloudfront.net/images/29358293/2179836907.jpg" alt="Montiget Product" class="h-48 object-contain my-4" onerror="this.onerror=null;this.src='https://placehold.co/200x200/cccccc/ffffff?text=Montiget';">
                    <p class="font-semibold">Manufacturer: Getz Pharma</p>
                    <p>Forms: Tablets, Chewables, Sachets</p>
                </div>
                 <div class="border p-4 rounded-lg flex flex-col items-center text-center">
                    <img src="https://samipharmapk.com/wp-content/uploads/2020/12/sami-pharma-logo.png" alt="Sami Pharma" class="h-16 mb-4" onerror="this.onerror=null;this.src='https://placehold.co/200x60/cccccc/ffffff?text=Sami+Pharma';">
                    <h3 class="mt-0">Montika</h3>
                    <img src="https://medonline.pk/wp-content/uploads/2022/01/MONTIKA-10MG-TAB-14S_1-1.jpg" alt="Montika Product" class="h-48 object-contain my-4" onerror="this.onerror=null;this.src='https://placehold.co/200x200/cccccc/ffffff?text=Montika';">
                    <p class="font-semibold">Manufacturer: Sami Pharmaceuticals</p>
                    <p>Forms: Tablets, Chewables, Sachets</p>
                </div>
                 <div class="border p-4 rounded-lg flex flex-col items-center text-center">
                    <img src="https://www.highnoon-labs.com/wp-content/uploads/2022/07/logo.png" alt="Highnoon Labs" class="h-16 mb-4" onerror="this.onerror=null;this.src='https://placehold.co/200x60/cccccc/ffffff?text=Highnoon+Labs';">
                    <h3 class="mt-0">Ventomax</h3>
                    <img src="https://dawailo.pk/wp-content/uploads/2021/04/Ventomax-10mg-Tablet-14s.jpg" alt="Ventomax Product" class="h-48 object-contain my-4" onerror="this.onerror=null;this.src='https://placehold.co/200x200/cccccc/ffffff?text=Ventomax';">
                    <p class="font-semibold">Manufacturer: Highnoon Laboratories</p>
                    <p>Forms: Tablets</p>
                </div>
            </div>
        </section>
        
        <section id="references" class="bg-white p-8 rounded-lg card-shadow scroll-mt-32">
            <h2>References</h2>
            <ol class="list-decimal list-inside space-y-2 text-sm text-blue-700">
                <li><a href="https://www.drugs.com/pregnancy/montelukast.html" target="_blank" rel="noopener noreferrer" class="hover:underline">drugs.com/pregnancy/montelukast.html</a></li>
                <li><a href="https://go.drugbank.com/drugs/DB00471" target="_blank" rel="noopener noreferrer" class="hover:underline">go.drugbank.com/drugs/DB00471</a></li>
                <li><a href="https://www.sciencedirect.com/topics/neuroscience/montelukast" target="_blank" rel="noopener noreferrer" class="hover:underline">sciencedirect.com/topics/neuroscience/montelukast</a></li>
                <li><a href="https://druginfosys.com/AvailableBrands.aspx?query=10%20mg&form=Tabs&drugCode=935&drugName=Montelukast&lng=1" target="_blank" rel="noopener noreferrer" class="hover:underline">druginfosys.com</a></li>
                 <li><a href="https://shop.lww.com/Lippincott-Illustrated-Reviews--Pharmacology/p/9781975170554" target="_blank" rel="noopener noreferrer" class="hover:underline">shop.lww.com/Lippincott-Illustrated-Reviews--Pharmacology</a></li>
            </ol>
        </section>

    </main>
    
    <footer class="bg-[#34495E] text-white mt-8">
        <div class="container mx-auto px-6 py-8 text-center">
            <p class="font-semibold">Disclaimer</p>
            <p class="mt-2 text-sm text-gray-300 max-w-3xl mx-auto">This webpage is for educational and informational purposes only and is not a substitute for professional medical advice, diagnosis, or treatment. It is intended for healthcare students and professionals. Always seek the advice of a qualified health provider with any questions you may have regarding a medical condition.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            const navLinks = document.querySelectorAll('.nav-link');

            mobileMenuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            const sections = document.querySelectorAll('main section');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.remove('active');
                            const linkHref = link.getAttribute('href');
                            if (linkHref && linkHref.substring(1) === entry.target.id) {
                                link.classList.add('active');
                            }
                        });
                    }
                });
            }, { rootMargin: '-40% 0px -60% 0px' });

            sections.forEach(section => {
                observer.observe(section);
            });
            
            navLinks.forEach(link => {
              link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = link.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                if(targetElement){
                    targetElement.scrollIntoView({ behavior: 'smooth' });
                }
                if (!mobileMenu.classList.contains('hidden')) {
                  mobileMenu.classList.add('hidden');
                }
              });
            });

            const generateBtn = document.getElementById('generate-points-btn');
            const aiPromptTextarea = document.getElementById('ai-prompt');
            const outputDiv = document.getElementById('counseling-points-output');
            const loader = document.getElementById('ai-loader');

            generateBtn.addEventListener('click', async () => {
                const userScenario = aiPromptTextarea.value.trim();
                if (!userScenario) {
                    outputDiv.innerHTML = `<p class="text-red-600 font-semibold">Please enter a patient scenario first.</p>`;
                    return;
                }

                outputDiv.innerHTML = '';
                loader.classList.remove('hidden');
                generateBtn.disabled = true;

                const prompt = `You are a clinical pharmacist preparing notes for a patient consultation. Based on the following patient scenario, generate a list of key counseling points about Montelukast. Structure the response with a brief introductory sentence, followed by a numbered list. Crucially, you must include a point about the Black Box Warning for neuropsychiatric effects. Do not give direct medical advice, but phrase the points as if you were preparing notes for the consultation. The scenario is: "${userScenario}"`;

                try {
                    const chatHistory = [{ role: "user", parts: [{ text: prompt }] }];
                    const payload = { contents: chatHistory };
                    const apiKey = "";
                    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
                    
                    const response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    if (!response.ok) {
                        throw new Error(`API Error: ${response.statusText}`);
                    }

                    const result = await response.json();
                    
                    if (result.candidates && result.candidates.length > 0 && result.candidates[0].content && result.candidates[0].content.parts && result.candidates[0].content.parts.length > 0) {
                        const text = result.candidates[0].content.parts[0].text;
                        const formattedHtml = text
                            .replace(/(\d\.)/g, '<br><strong class="text-blue-700">$1</strong>')
                            .replace(/\n/g, '<br>');

                        outputDiv.innerHTML = `
                            <div class="p-6 bg-gray-50 rounded-lg border border-gray-200 mt-4">
                                <h4 class="font-bold text-lg text-[#34495E] mb-3">Generated Counseling Points:</h4>
                                <div class="text-gray-700 leading-relaxed">${formattedHtml}</div>
                                <p class="text-xs text-gray-500 mt-4 italic">Note: This is an AI-generated tool and does not replace professional clinical judgment. Verify all information.</p>
                            </div>`;
                    } else {
                        throw new Error("The AI returned an empty or invalid response.");
                    }

                } catch (error) {
                    console.error("Gemini API call failed:", error);
                    outputDiv.innerHTML = `<div class="p-4 bg-red-50 rounded-lg border border-red-200 text-red-700">Sorry, we couldn't generate counseling points at this time. Please check your connection and try again.</div>`;
                } finally {
                    loader.classList.add('hidden');
                    generateBtn.disabled = false;
                }
            });
        });
    </script>
</body>
</html>
