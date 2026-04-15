# Indication Formula for EULAR Planner

## How to use

1. Paste the formula below into cell **L342**
2. Drag down to fill all remaining rows

The formula reads the **Title** column (G) and returns all matching indications, separated by commas. If no indication is found, it returns `N/A`.

## Formula

```
=LET(r,TEXTJOIN(", ",TRUE,IF(OR(ISNUMBER(SEARCH("Rheumatoid Arthritis",G342)),ISNUMBER(SEARCH(" RA ",G342)),ISNUMBER(SEARCH(" RA,",G342)),ISNUMBER(SEARCH(" RA:",G342)),ISNUMBER(SEARCH(" RA-",G342)),ISNUMBER(SEARCH("(RA)",G342)),RIGHT(G342,3)=" RA"),"RA",""),IF(OR(ISNUMBER(SEARCH("Psoriatic",G342)),ISNUMBER(SEARCH(" PsA ",G342)),ISNUMBER(SEARCH(" PsA,",G342)),ISNUMBER(SEARCH(" PsA-",G342)),ISNUMBER(SEARCH("(PsA)",G342)),RIGHT(G342,4)=" PsA"),"PsA",""),IF(OR(ISNUMBER(SEARCH("Psoriasis",G342)),ISNUMBER(SEARCH(" PsO",G342))),"PsO",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G342)),ISNUMBER(SEARCH("axial",G342))),ISNUMBER(SEARCH("axSpA",G342))),"AxSpA",""),IF(OR(AND(ISNUMBER(SEARCH("Spondyloarthritis",G342)),ISNUMBER(SEARCH("peripheral",G342))),ISNUMBER(SEARCH("pSpA",G342))),"pSpA",""),IF(ISNUMBER(SEARCH("Ankylosing Spondylitis",G342)),"AS",""),IF(AND(OR(ISNUMBER(SEARCH("Spondyloarthritis",G342)),ISNUMBER(SEARCH("Spondylarthritis",G342)),ISNUMBER(SEARCH(" SpA ",G342)),ISNUMBER(SEARCH(" SpA,",G342)),ISNUMBER(SEARCH(" SpA:",G342)),ISNUMBER(SEARCH(" SpA.",G342)),ISNUMBER(SEARCH("(SpA)",G342)),RIGHT(G342,4)=" SpA"),ISERROR(SEARCH("axial",G342)),ISERROR(SEARCH("peripheral",G342)),ISERROR(SEARCH("Ankylosing",G342)),ISERROR(SEARCH("axSpA",G342))),"SpA",""),IF(OR(ISNUMBER(SEARCH("Systemic Sclerosis",G342)),ISNUMBER(SEARCH("Scleroderma",G342)),ISNUMBER(SEARCH(" SSc",G342)),ISNUMBER(SEARCH("(SSc)",G342))),"SSc",""),IF(OR(AND(ISNUMBER(SEARCH("Lupus Erythematosus",G342)),ISERROR(SEARCH("Cutaneous Lupus",G342))),ISNUMBER(SEARCH("Systemic Lupus",G342)),ISNUMBER(SEARCH(" SLE ",G342)),ISNUMBER(SEARCH(" SLE,",G342)),ISNUMBER(SEARCH(" SLE:",G342)),ISNUMBER(SEARCH("(SLE)",G342)),RIGHT(G342,4)=" SLE",AND(ISNUMBER(SEARCH("Lupus",G342)),ISERROR(SEARCH("Lupus Nephritis",G342)),ISERROR(SEARCH("Cutaneous Lupus",G342)),ISERROR(SEARCH("Lupus Erythematosus",G342)))),"SLE",""),IF(OR(ISNUMBER(SEARCH("Lupus Nephritis",G342)),ISNUMBER(SEARCH(" LN ",G342)),ISNUMBER(SEARCH("(LN)",G342))),"LN",""),IF(ISNUMBER(SEARCH("Cutaneous Lupus",G342)),"CLE",""),IF(OR(ISNUMBER(SEARCH("Mixed Connective Tissue",G342)),ISNUMBER(SEARCH("MCTD",G342))),"MCTD",""),IF(OR(ISNUMBER(SEARCH("Juvenile Idiopathic Arthritis",G342)),ISNUMBER(SEARCH(" JIA",G342)),ISNUMBER(SEARCH("(JIA)",G342))),"JIA",""),IF(OR(ISNUMBER(SEARCH("Giant Cell Arteritis",G342)),ISNUMBER(SEARCH(" GCA ",G342)),ISNUMBER(SEARCH(" GCA,",G342)),ISNUMBER(SEARCH(" GCA:",G342)),ISNUMBER(SEARCH("(GCA)",G342)),ISNUMBER(SEARCH("-GCA",G342))),"GCA",""),IF(OR(ISNUMBER(SEARCH("Polymyalgia Rheumatica",G342)),ISNUMBER(SEARCH(" PMR ",G342)),ISNUMBER(SEARCH(" PMR,",G342)),ISNUMBER(SEARCH("(PMR)",G342))),"PMR",""),IF(ISNUMBER(SEARCH("Takayasu",G342)),"TAK",""),IF(OR(ISNUMBER(SEARCH(" ANCA",G342)),ISNUMBER(SEARCH(" AAV",G342)),ISNUMBER(SEARCH("(AAV)",G342))),"AAV",""),IF(OR(ISNUMBER(SEARCH("EGPA",G342)),ISNUMBER(SEARCH("Eosinophilic Granulomatosis",G342))),"EGPA",""),IF(OR(ISNUMBER(SEARCH("Behçet",G342)),ISNUMBER(SEARCH("Behcet",G342))),"BD",""),IF(OR(ISNUMBER(SEARCH("Sjögren",G342)),ISNUMBER(SEARCH("Sjogren",G342))),"SjD",""),IF(OR(ISNUMBER(SEARCH("Myositis",G342)),ISNUMBER(SEARCH("Myopath",G342)),ISNUMBER(SEARCH(" IIM",G342))),"IIM",""),IF(OR(ISNUMBER(SEARCH("Interstitial Lung",G342)),ISNUMBER(SEARCH("-ILD",G342)),ISNUMBER(SEARCH(" ILD ",G342)),ISNUMBER(SEARCH(" ILD,",G342))),"ILD",""),IF(ISNUMBER(SEARCH("Antiphospholipid",G342)),"APS",""),IF(ISNUMBER(SEARCH("IgG4",G342)),"IgG4-RD",""),IF(OR(ISNUMBER(SEARCH("Still's",G342)),ISNUMBER(SEARCH("Still D",G342)),ISNUMBER(SEARCH("AOSD",G342))),"AOSD",""),IF(OR(ISNUMBER(SEARCH("Familial Mediterranean Fever",G342)),ISNUMBER(SEARCH(" FMF",G342))),"FMF",""),IF(OR(ISNUMBER(SEARCH("CPPD",G342)),ISNUMBER(SEARCH("Calcium Pyrophosphate",G342))),"CPPD",""),IF(ISNUMBER(SEARCH("Gout",G342)),"Gout",""),IF(ISNUMBER(SEARCH("Osteoarthritis",G342)),"OA",""),IF(ISNUMBER(SEARCH("Osteoporosis",G342)),"OP",""),IF(ISNUMBER(SEARCH("Fibromyalgia",G342)),"FM",""),IF(ISNUMBER(SEARCH("Uveitis",G342)),"Uveitis",""),IF(ISNUMBER(SEARCH("Raynaud",G342)),"Raynaud","")),IF(r="","N/A",r))
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
