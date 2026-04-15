# Indication Formula for EULAR Planner

## How to use

1. Paste the formula below into cell **L3** (or whichever row your data starts)
2. Replace `G3` with the appropriate row if needed
3. Drag down to fill all rows

The formula reads the **Title** column (G) and returns all matching indications, separated by commas. If no indication is found, it returns `N/A`.

## Formula

```
=LET(r,TEXTJOIN(", ",TRUE,IF(OR(ISNUMBER(SEARCH("Rheumatoid Arthritis",G3)),ISNUMBER(SEARCH(" RA ",G3)),ISNUMBER(SEARCH(" RA,",G3)),ISNUMBER(SEARCH(" RA:",G3)),ISNUMBER(SEARCH(" RA-",G3)),ISNUMBER(SEARCH("(RA)",G3)),RIGHT(G3,3)=" RA"),"RA",""),IF(OR(ISNUMBER(SEARCH("Psoriatic",G3)),ISNUMBER(SEARCH(" PsA ",G3)),ISNUMBER(SEARCH(" PsA,",G3)),ISNUMBER(SEARCH(" PsA-",G3)),ISNUMBER(SEARCH("(PsA)",G3)),RIGHT(G3,4)=" PsA"),"PsA",""),IF(OR(ISNUMBER(SEARCH("Psoriasis",G3)),ISNUMBER(SEARCH(" PsO",G3))),"PsO",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G3)),ISNUMBER(SEARCH("axial",G3))),ISNUMBER(SEARCH("axSpA",G3))),"AxSpA",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G3)),ISNUMBER(SEARCH("peripheral",G3))),ISNUMBER(SEARCH("pSpA",G3))),"pSpA",""),IF(ISNUMBER(SEARCH("Ankylosing Spondylitis",G3)),"AS",""),IF(AND(OR(ISNUMBER(SEARCH("Spondyloarthritis",G3)),ISNUMBER(SEARCH("Spondylarthritis",G3)),ISNUMBER(SEARCH(" SpA",G3))),ISERROR(SEARCH("axial",G3)),ISERROR(SEARCH("peripheral",G3)),ISERROR(SEARCH("Ankylosing",G3)),ISERROR(SEARCH("axSpA",G3))),"SpA",""),IF(OR(ISNUMBER(SEARCH("Systemic Sclerosis",G3)),ISNUMBER(SEARCH("Scleroderma",G3)),ISNUMBER(SEARCH(" SSc",G3)),ISNUMBER(SEARCH("(SSc)",G3))),"SSc",""),IF(OR(AND(ISNUMBER(SEARCH("Lupus Erythematosus",G3)),ISERROR(SEARCH("Cutaneous Lupus",G3))),ISNUMBER(SEARCH("Systemic Lupus",G3)),ISNUMBER(SEARCH(" SLE ",G3)),ISNUMBER(SEARCH(" SLE,",G3)),ISNUMBER(SEARCH(" SLE:",G3)),ISNUMBER(SEARCH("(SLE)",G3)),RIGHT(G3,4)=" SLE",AND(ISNUMBER(SEARCH("Lupus",G3)),ISERROR(SEARCH("Lupus Nephritis",G3)),ISERROR(SEARCH("Cutaneous Lupus",G3)),ISERROR(SEARCH("Lupus Erythematosus",G3)))),"SLE",""),IF(OR(ISNUMBER(SEARCH("Lupus Nephritis",G3)),ISNUMBER(SEARCH(" LN ",G3)),ISNUMBER(SEARCH("(LN)",G3))),"LN",""),IF(ISNUMBER(SEARCH("Cutaneous Lupus",G3)),"CLE",""),IF(OR(ISNUMBER(SEARCH("Mixed Connective Tissue",G3)),ISNUMBER(SEARCH("MCTD",G3))),"MCTD",""),IF(OR(ISNUMBER(SEARCH("Juvenile Idiopathic Arthritis",G3)),ISNUMBER(SEARCH(" JIA",G3)),ISNUMBER(SEARCH("(JIA)",G3))),"JIA",""),IF(OR(ISNUMBER(SEARCH("Giant Cell Arteritis",G3)),ISNUMBER(SEARCH(" GCA ",G3)),ISNUMBER(SEARCH(" GCA,",G3)),ISNUMBER(SEARCH(" GCA:",G3)),ISNUMBER(SEARCH("(GCA)",G3)),ISNUMBER(SEARCH("-GCA",G3))),"GCA",""),IF(OR(ISNUMBER(SEARCH("Polymyalgia Rheumatica",G3)),ISNUMBER(SEARCH(" PMR ",G3)),ISNUMBER(SEARCH(" PMR,",G3)),ISNUMBER(SEARCH("(PMR)",G3))),"PMR",""),IF(ISNUMBER(SEARCH("Takayasu",G3)),"TAK",""),IF(OR(ISNUMBER(SEARCH(" ANCA",G3)),ISNUMBER(SEARCH(" AAV",G3)),ISNUMBER(SEARCH("(AAV)",G3))),"AAV",""),IF(OR(ISNUMBER(SEARCH("EGPA",G3)),ISNUMBER(SEARCH("Eosinophilic Granulomatosis",G3))),"EGPA",""),IF(OR(ISNUMBER(SEARCH("Behçet",G3)),ISNUMBER(SEARCH("Behcet",G3))),"BD",""),IF(OR(ISNUMBER(SEARCH("Sjögren",G3)),ISNUMBER(SEARCH("Sjogren",G3))),"SjD",""),IF(OR(ISNUMBER(SEARCH("Myositis",G3)),ISNUMBER(SEARCH("Myopath",G3)),ISNUMBER(SEARCH(" IIM",G3))),"IIM",""),IF(OR(ISNUMBER(SEARCH("Interstitial Lung",G3)),ISNUMBER(SEARCH("-ILD",G3)),ISNUMBER(SEARCH(" ILD ",G3)),ISNUMBER(SEARCH(" ILD,",G3))),"ILD",""),IF(ISNUMBER(SEARCH("Antiphospholipid",G3)),"APS",""),IF(ISNUMBER(SEARCH("IgG4",G3)),"IgG4-RD",""),IF(OR(ISNUMBER(SEARCH("Still's",G3)),ISNUMBER(SEARCH("Still D",G3)),ISNUMBER(SEARCH("AOSD",G3))),"AOSD",""),IF(OR(ISNUMBER(SEARCH("Familial Mediterranean Fever",G3)),ISNUMBER(SEARCH(" FMF",G3))),"FMF",""),IF(OR(ISNUMBER(SEARCH("CPPD",G3)),ISNUMBER(SEARCH("Calcium Pyrophosphate",G3))),"CPPD",""),IF(ISNUMBER(SEARCH("Gout",G3)),"Gout",""),IF(ISNUMBER(SEARCH("Osteoarthritis",G3)),"OA",""),IF(ISNUMBER(SEARCH("Osteoporosis",G3)),"OP",""),IF(ISNUMBER(SEARCH("Fibromyalgia",G3)),"FM",""),IF(ISNUMBER(SEARCH("Uveitis",G3)),"Uveitis",""),IF(ISNUMBER(SEARCH("Raynaud",G3)),"Raynaud","")),IF(r="","N/A",r))
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
