{\rtf1\ansi\ansicpg1252\cocoartf2580
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 let preference = '';\
\
function setPreference(choice) \{\
    preference = choice;\
    document.getElementById('camera-section').style.display = 'block';\
\}\
\
function startScan() \{\
    const video = document.getElementById('video');\
    if (navigator.mediaDevices.getUserMedia) \{\
        navigator.mediaDevices.getUserMedia(\{ video: true \})\
            .then(function(stream) \{\
                video.srcObject = stream;\
                simulateScan();\
            \})\
            .catch(function(err) \{\
                alert("Camera access denied: " + err);\
            \});\
    \}\
\}\
\
function simulateScan() \{\
    setTimeout(() => \{\
        const results = document.getElementById('results');\
        let shades = \{\
            exact: [\
                \{ brand: 'MAC', shade: 'NC25', color: '#F1C27D' \},\
                \{ brand: 'Fenty', shade: '240', color: '#E0B687' \},\
                \{ brand: 'NARS', shade: 'Punjab', color: '#D9A066' \}\
            ],\
            lighter: [\
                \{ brand: 'MAC', shade: 'NC20', color: '#F5D0A9' \},\
                \{ brand: 'Fenty', shade: '230', color: '#E8CBAA' \},\
                \{ brand: 'NARS', shade: 'Syracuse', color: '#E4B67F' \}\
            ],\
            orange: [\
                \{ brand: 'MAC', shade: 'NC30', color: '#DFA96B' \},\
                \{ brand: 'Fenty', shade: '270', color: '#D9A066' \},\
                \{ brand: 'NARS', shade: 'Gobi', color: '#D3A16D' \}\
            ]\
        \};\
\
        let selectedShades = shades[preference] || shades['exact'];\
\
        let html = '<h3>Your Recommended Shades:</h3>';\
        selectedShades.forEach(s => \{\
            html += `<div><strong>$\{s.brand\}:</strong> $\{s.shade\} <div class="shade" style="background-color:$\{s.color\};"></div></div>`;\
        \});\
\
        results.innerHTML = html;\
    \}, 3000); // simulate scanning delay\
\}}
