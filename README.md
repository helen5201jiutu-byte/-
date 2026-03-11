<div class="grid">
    <div class="input-group full-width">
        <label>打包方式</label>
        <select id="packType" onchange="toggleInputs()">
            <option value="roll">卷装 (按正方截面计算体积)</option>
            <option value="flat">折叠/箱装 (标准长方体)</option>
        </select>
    </div>

    <div class="input-group">
        <label id="dim1Label">卷轴长度 (cm)</label>
        <input type="number" id="dim1" placeholder="L">
    </div>

    <div class="input-group">
        <label id="dim2Label">直径 (cm)</label>
        <input type="number" id="dim2" placeholder="D/W">
    </div>

    <div class="input-group" id="heightGroup" style="display:none;">
        <label>高度 (cm)</label>
        <input type="number" id="dim3" placeholder="H">
    </div>

    <div class="input-group">
        <label>单件测量实重 (KG)</label>
        <input type="number" id="singleWeight" placeholder="称重结果">
    </div>

    <div class="input-group">
        <label>总件数/卷数</label>
        <input type="number" id="qty" value="1">
    </div>

    <div class="input-group">
        <label>额外包装/托盘重 (KG)</label>
        <input type="number" id="extraWeight" value="0" placeholder="无则填0">
    </div>

    <div class="input-group">
        <label>计重系数 (Factor)</label>
        <select id="vFactor">
            <option value="5000">快递 (5000)</option>
            <option value="6000">空运 (6000)</option>
            <option value="4000">特殊专线 (4000)</option>
        </select>
    </div>
</div>

<button onclick="calculate()">计算最终货运数据</button>

<div id="result" class="result-box">
    <div class="res-item"><span>总体积:</span> <span id="totalCbm">0</span> CBM</div>
    <div class="res-item"><span>总实重 (Actual):</span> <span id="actualWeight">0</span> KG</div>
    <div class="res-item"><span>总体积重 (Vol.):</span> <span id="volWeight">0</span> KG</div>
    
    <div class="final-panel">
        <h3>货物最终计费重量 (Chargeable Weight)</h3>
        <div class="final-val" id="finalWeight">0<span class="final-unit">KG</span></div>
        <span id="weightNote" class="warning-text"></span>
    </div>

    <div class="res-item" style="margin-top:15px; border:none; font-size:14px;">
        <span>货运建议:</span> <strong id="shippingAdv" style="color:var(--primary)">--</strong>
    </div>
</div>
