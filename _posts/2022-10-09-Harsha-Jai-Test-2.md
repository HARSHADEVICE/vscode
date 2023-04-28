---
keywords: fastai
title: Title
nb_path: _notebooks/2022-10-09-Harsha-Jai-Test-2.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-10-09-Harsha-Jai-Test-2.ipynb
-->

<div class="container" id="notebook-container">
        
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">requests</span>
<span class="kn">import</span> <span class="nn">json</span>
<span class="kn">from</span> <span class="nn">pandas.io.json</span> <span class="kn">import</span> <span class="n">json_normalize</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span> 

<span class="n">url</span> <span class="o">=</span> <span class="s2">&quot;https://bloomberg-market-and-financial-news.p.rapidapi.com/stock/get-financials&quot;</span>

<span class="n">querystring</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;id&quot;</span><span class="p">:</span><span class="s2">&quot;aapl:us&quot;</span><span class="p">}</span>

<span class="n">headers</span> <span class="o">=</span> <span class="p">{</span>
	<span class="s2">&quot;X-RapidAPI-Key&quot;</span><span class="p">:</span> <span class="s2">&quot;da575c39f6mshc8ce88363a3e559p1050a9jsnfe4daeb7274a&quot;</span><span class="p">,</span>
	<span class="s2">&quot;X-RapidAPI-Host&quot;</span><span class="p">:</span> <span class="s2">&quot;bloomberg-market-and-financial-news.p.rapidapi.com&quot;</span>
<span class="p">}</span>

<span class="n">response</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">request</span><span class="p">(</span><span class="s2">&quot;GET&quot;</span><span class="p">,</span> <span class="n">url</span><span class="p">,</span> <span class="n">headers</span><span class="o">=</span><span class="n">headers</span><span class="p">,</span> <span class="n">params</span><span class="o">=</span><span class="n">querystring</span><span class="p">)</span>

<span class="n">data</span> <span class="o">=</span> <span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>

<span class="c1">#df = pd.read_json(data)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#39;result&#39;: [{&#39;name&#39;: &#39;Income Statement&#39;, &#39;securityID&#39;: &#39;AAPL:US&#39;, &#39;timeBasedSheets&#39;: [{&#39;name&#39;: &#39;Quarterly&#39;, &#39;columnHeadings&#39;: [&#39;12/2021&#39;, &#39;3/2022&#39;, &#39;6/2022&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Revenue&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [123945000000.0, 97278000000.0, 82959000000.0]}, {&#39;name&#39;: &#39;Net Income&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [34630000000.0, 25010000000.0, 19442000000.0]}, {&#39;name&#39;: &#39;Profit Margin&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: True, &#39;values&#39;: [27.9398, 25.7098, 23.4357]}]}, {&#39;name&#39;: &#39;Annual&#39;, &#39;columnHeadings&#39;: [&#39;2019&#39;, &#39;2020&#39;, &#39;2021&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Revenue&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [260174000000.0, 274515000000.0, 365817000000.0]}, {&#39;name&#39;: &#39;Net Income&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [55256000000.0, 57411000000.0, 94680000000.0]}, {&#39;name&#39;: &#39;Profit Margin&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: True, &#39;values&#39;: [21.2381, 20.9136, 25.8818]}]}]}, {&#39;name&#39;: &#39;Balance Sheet&#39;, &#39;securityID&#39;: &#39;AAPL:US&#39;, &#39;timeBasedSheets&#39;: [{&#39;name&#39;: &#39;Quarterly&#39;, &#39;columnHeadings&#39;: [&#39;12/2021&#39;, &#39;3/2022&#39;, &#39;6/2022&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Total Assets&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [381191000000.0, 350662000000.0, 336309000000.0]}, {&#39;name&#39;: &#39;Total Liabilities&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [309259000000.0, 283263000000.0, 278202000000.0]}, {&#39;name&#39;: &#39;Debt to Assets&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: True, &#39;values&#39;: [32.2143, 34.2156, 35.5896]}]}, {&#39;name&#39;: &#39;Annual&#39;, &#39;columnHeadings&#39;: [&#39;2019&#39;, &#39;2020&#39;, &#39;2021&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Total Assets&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [338516000000.0, 323888000000.0, 351002000000.0]}, {&#39;name&#39;: &#39;Total Liabilities&#39;, &#39;chartType&#39;: &#39;bar&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [248028000000.0, 258549000000.0, 287912000000.0]}, {&#39;name&#39;: &#39;Debt to Assets&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: True, &#39;values&#39;: [31.9178, 37.7532, 38.8949]}]}]}, {&#39;name&#39;: &#39;Cash Flow&#39;, &#39;securityID&#39;: &#39;AAPL:US&#39;, &#39;timeBasedSheets&#39;: [{&#39;name&#39;: &#39;Quarterly&#39;, &#39;columnHeadings&#39;: [&#39;12/2021&#39;, &#39;3/2022&#39;, &#39;6/2022&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Operating&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [46966000000.0, 28166000000.0, 22892000000.0]}, {&#39;name&#39;: &#39;Investing&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [-16106000000.0, -9265000000.0, 4234000000.0]}, {&#39;name&#39;: &#39;Financing&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [-28159000000.0, -28351000000.0, -27445000000.0]}]}, {&#39;name&#39;: &#39;Annual&#39;, &#39;columnHeadings&#39;: [&#39;2019&#39;, &#39;2020&#39;, &#39;2021&#39;], &#39;chartData&#39;: [{&#39;name&#39;: &#39;Operating&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [69391000000.0, 80674000000.0, 104038000000.0]}, {&#39;name&#39;: &#39;Investing&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [45896000000.0, -4289000000.0, -14545000000.0]}, {&#39;name&#39;: &#39;Financing&#39;, &#39;chartType&#39;: &#39;line&#39;, &#39;isPercentage&#39;: False, &#39;values&#39;: [-90976000000.0, -86820000000.0, -93353000000.0]}]}]}]}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<ul>
<li>Example Test this failed :(</li>
</ul>

</div>
</div>
</div>
</div>
 
