# Indication Formula for EULAR Planner

## How to use

1. Paste the formula below into cell **L283**
2. Drag down to fill all remaining rows

The formula reads the **Title** column (G) and returns all matching indications, separated by commas. If no indication is found, it returns `N/A`.

## Formula

```
=LET(r,TEXTJOIN(", ",TRUE,IF(OR(ISNUMBER(SEARCH("Rheumatoid Arthritis",G283)),ISNUMBER(SEARCH(" RA ",G283)),ISNUMBER(SEARCH(" RA,",G283)),ISNUMBER(SEARCH(" RA:",G283)),ISNUMBER(SEARCH(" RA-",G283)),ISNUMBER(SEARCH("(RA)",G283)),RIGHT(G283,3)=" RA"),"RA",""),IF(OR(ISNUMBER(SEARCH("Psoriatic",G283)),ISNUMBER(SEARCH(" PsA ",G283)),ISNUMBER(SEARCH(" PsA,",G283)),ISNUMBER(SEARCH(" PsA-",G283)),ISNUMBER(SEARCH("(PsA)",G283)),RIGHT(G283,4)=" PsA"),"PsA",""),IF(OR(ISNUMBER(SEARCH("Psoriasis",G283)),ISNUMBER(SEARCH(" PsO",G283))),"PsO",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G283)),ISNUMBER(SEARCH("axial",G283))),ISNUMBER(SEARCH("axSpA",G283))),"AxSpA",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G283)),ISNUMBER(SEARCH("peripheral",G283))),ISNUMBER(SEARCH("pSpA",G283))),"pSpA",""),IF(ISNUMBER(SEARCH("Ankylosing Spondylitis",G283)),"AS",""),IF(AND(OR(ISNUMBER(SEARCH("Spondyloarthritis",G283)),ISNUMBER(SEARCH("Spondylarthritis",G283)),ISNUMBER(SEARCH(" SpA",G283))),ISERROR(SEARCH("axial",G283)),ISERROR(SEARCH("peripheral",G283)),ISERROR(SEARCH("Ankylosing",G283)),ISERROR(SEARCH("axSpA",G283))),"SpA",""),IF(OR(ISNUMBER(SEARCH("Systemic Sclerosis",G283)),ISNUMBER(SEARCH("Scleroderma",G283)),ISNUMBER(SEARCH(" SSc",G283)),ISNUMBER(SEARCH("(SSc)",G283))),"SSc",""),IF(OR(AND(ISNUMBER(SEARCH("Lupus Erythematosus",G283)),ISERROR(SEARCH("Cutaneous Lupus",G283))),ISNUMBER(SEARCH("Systemic Lupus",G283)),ISNUMBER(SEARCH(" SLE ",G283)),ISNUMBER(SEARCH(" SLE,",G283)),ISNUMBER(SEARCH(" SLE:",G283)),ISNUMBER(SEARCH("(SLE)",G283)),RIGHT(G283,4)=" SLE",AND(ISNUMBER(SEARCH("Lupus",G283)),ISERROR(SEARCH("Lupus Nephritis",G283)),ISERROR(SEARCH("Cutaneous Lupus",G283)),ISERROR(SEARCH("Lupus Erythematosus",G283)))),"SLE",""),IF(OR(ISNUMBER(SEARCH("Lupus Nephritis",G283)),ISNUMBER(SEARCH(" LN ",G283)),ISNUMBER(SEARCH("(LN)",G283))),"LN",""),IF(ISNUMBER(SEARCH("Cutaneous Lupus",G283)),"CLE",""),IF(OR(ISNUMBER(SEARCH("Mixed Connective Tissue",G283)),ISNUMBER(SEARCH("MCTD",G283))),"MCTD",""),IF(OR(ISNUMBER(SEARCH("Juvenile Idiopathic Arthritis",G283)),ISNUMBER(SEARCH(" JIA",G283)),ISNUMBER(SEARCH("(JIA)",G283))),"JIA",""),IF(OR(ISNUMBER(SEARCH("Giant Cell Arteritis",G283)),ISNUMBER(SEARCH(" GCA ",G283)),ISNUMBER(SEARCH(" GCA,",G283)),ISNUMBER(SEARCH(" GCA:",G283)),ISNUMBER(SEARCH("(GCA)",G283)),ISNUMBER(SEARCH("-GCA",G283))),"GCA",""),IF(OR(ISNUMBER(SEARCH("Polymyalgia Rheumatica",G283)),ISNUMBER(SEARCH(" PMR ",G283)),ISNUMBER(SEARCH(" PMR,",G283)),ISNUMBER(SEARCH("(PMR)",G283))),"PMR",""),IF(ISNUMBER(SEARCH("Takayasu",G283)),"TAK",""),IF(OR(ISNUMBER(SEARCH(" ANCA",G283)),ISNUMBER(SEARCH(" AAV",G283)),ISNUMBER(SEARCH("(AAV)",G283))),"AAV",""),IF(OR(ISNUMBER(SEARCH("EGPA",G283)),ISNUMBER(SEARCH("Eosinophilic Granulomatosis",G283))),"EGPA",""),IF(OR(ISNUMBER(SEARCH("Behçet",G283)),ISNUMBER(SEARCH("Behcet",G283))),"BD",""),IF(OR(ISNUMBER(SEARCH("Sjögren",G283)),ISNUMBER(SEARCH("Sjogren",G283))),"SjD",""),IF(OR(ISNUMBER(SEARCH("Myositis",G283)),ISNUMBER(SEARCH("Myopath",G283)),ISNUMBER(SEARCH(" IIM",G283))),"IIM",""),IF(OR(ISNUMBER(SEARCH("Interstitial Lung",G283)),ISNUMBER(SEARCH("-ILD",G283)),ISNUMBER(SEARCH(" ILD ",G283)),ISNUMBER(SEARCH(" ILD,",G283))),"ILD",""),IF(ISNUMBER(SEARCH("Antiphospholipid",G283)),"APS",""),IF(ISNUMBER(SEARCH("IgG4",G283)),"IgG4-RD",""),IF(OR(ISNUMBER(SEARCH("Still's",G283)),ISNUMBER(SEARCH("Still D",G283)),ISNUMBER(SEARCH("AOSD",G283))),"AOSD",""),IF(OR(ISNUMBER(SEARCH("Familial Mediterranean Fever",G283)),ISNUMBER(SEARCH(" FMF",G283))),"FMF",""),IF(OR(ISNUMBER(SEARCH("CPPD",G283)),ISNUMBER(SEARCH("Calcium Pyrophosphate",G283))),"CPPD",""),IF(ISNUMBER(SEARCH("Gout",G283)),"Gout",""),IF(ISNUMBER(SEARCH("Osteoarthritis",G283)),"OA",""),IF(ISNUMBER(SEARCH("Osteoporosis",G283)),"OP",""),IF(ISNUMBER(SEARCH("Fibromyalgia",G283)),"FM",""),IF(ISNUMBER(SEARCH("Uveitis",G283)),"Uveitis",""),IF(ISNUMBER(SEARCH("Raynaud",G283)),"Raynaud","")),IF(r="","N/A",r))
```

## Covered Indications (33 categories)

| Abbreviation | Keywords Matched |
|---|---|
| **RA** | Rheumatoid Arthritis, " RA " abbreviation patterns |
| **PsA** | Psoriatic (Arthritis/Disease), " PsA " abbreviation patterns |
| **PsO** | Psoriasis |
| **AxSpA** | Axial Spondyloarthritis, axSpA |
| **pSpA** | Peripheral Spondyloarthritis, pSpA |
| **AS** | Ankylosing Spondylitis |
| **SpA** | Spondyloarthritis (generic, when no axial/peripheral/ankylosing qualifier) |
| **SSc** | Systemic Sclerosis, Scleroderma, SSc |
| **SLE** | Lupus Erythematosus (non-cutaneous), Systemic Lupus, SLE, bare "Lupus" |
| **LN** | Lupus Nephritis |
| **CLE** | Cutaneous Lupus |
| **MCTD** | Mixed Connective Tissue Disease |
| **JIA** | Juvenile Idiopathic Arthritis |
| **GCA** | Giant Cell Arteritis |
| **PMR** | Polymyalgia Rheumatica |
| **TAK** | Takayasu (Arteritis) |
| **AAV** | ANCA-Associated Vasculitis |
| **EGPA** | Eosinophilic Granulomatosis with Polyangiitis |
| **BD** | Behcet's Disease (Behçet / Behcet) |
| **SjD** | Sjogren's Disease (Sjögren / Sjogren) |
| **IIM** | Idiopathic Inflammatory Myopathy (Myositis, Myopathy, IIM) |
| **ILD** | Interstitial Lung Disease |
| **APS** | Antiphospholipid Syndrome |
| **IgG4-RD** | IgG4-Related Disease |
| **AOSD** | Adult-Onset Still's Disease |
| **FMF** | Familial Mediterranean Fever |
| **CPPD** | Calcium Pyrophosphate Deposition Disease |
| **Gout** | Gout |
| **OA** | Osteoarthritis |
| **OP** | Osteoporosis |
| **FM** | Fibromyalgia |
| **Uveitis** | Uveitis |
| **Raynaud** | Raynaud's |

## Notes

- **Multi-match**: Returns all matching indications separated by ", " (e.g., "RA, ILD" or "SLE, LN")
- **Case-insensitive**: SEARCH is case-insensitive, so "rheumatoid arthritis" and "Rheumatoid Arthritis" both match
- **Abbreviation-aware**: Catches both full disease names and common abbreviations (RA, SLE, GCA, etc.) with word-boundary patterns to avoid false positives
- **Lupus logic**: Distinguishes between SLE, LN, and CLE - "Cutaneous Lupus Erythematosus" returns CLE (not SLE), "Lupus Nephritis" returns LN
- **SpA logic**: Differentiates AxSpA (axial), pSpA (peripheral), AS (ankylosing), and generic SpA based on qualifiers in the title
- **Requires Excel 365 or Excel 2021+** (uses LET and TEXTJOIN functions)
