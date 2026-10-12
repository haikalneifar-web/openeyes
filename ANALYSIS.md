# OpenEyes: feature analysis

**In short:** OpenEyes is strong at clinical documentation for ophthalmology. It is weaker as a complete hospital system, and it is built around the UK health service (NHS). Its best features are the drawing tool, the cataract workflow and the trend views over time. The main limits are scheduling and billing, which it leaves to other systems, and how much setup work is needed to use it outside the UK.

## Strengths

| Area | What it does well | Why it matters |
|---|---|---|
| **EyeDraw** | More than 150 eye-specific drawings, and each drawing writes its own report text. | Most general EPRs can't do this. Clinicians draw what they see and still get structured data. |
| **Cataract workflow** | Biometry → lens choice → operation note → theatre whiteboard → national audit, with data flowing from one step to the next. | This is the most complete end-to-end workflow. It avoids typing the same data twice and reduces lens-selection errors. |
| **Tracking over time** | OEscape charts acuity, eye pressure, retinal thickness and injections across visits, linked to the OCT scans. | Glaucoma and medical retina follow-up depend on trends, and this suits them well. |
| **Virtual clinics** | Review lists, ticket queues, automatic letters and prescriptions. | One NHS trust reported cutting its glaucoma follow-up backlog by 68%. |
| **Data entry speed** | Popup selection panels (the project claims up to 50% fewer clicks) and a dark theme for dim clinic rooms. | Clinicians designed it for busy clinics. |
| **Analytics** | Real-time audit to the UK national ophthalmology database standard, waiting-time charts that flag patients lost to follow-up, and drill-down to individual patients. | Quality reporting comes built in rather than as an add-on. |
| **Architecture** | Records are organised as patient → episode → event → element, with one module per event type. | You can add new event types without touching the core code. |

## Gaps and weaknesses

1. **It isn't a complete hospital system.** It relies on a separate patient administration system for appointments and demographics. There is no documented billing, invoicing or insurance feature, and no booking calendar. A private clinic or a hospital without that kind of system would need to add it.
2. **It is built around the UK.** Many features assume NHS processes:
   - letters to GPs
   - the UK visual impairment certificate
   - the NHS 18-week waiting-time target
   - the UK national cataract audit
   - funding applications for treatments
   - English-only interface text

   No translation support is documented. Using it in another country would mean adapting the letter templates, drug lists, forms and language.
3. **Interoperability is unclear.** It connects to devices through DICOM and has an API for the patient administration system. There is no clear evidence of FHIR or HL7 support.
4. **The technology is ageing.** It runs on the Yii 1.1 framework, which is very old, and PHP 7.4 to 8.1 (PHP 7.4 is no longer supported). That adds security and maintenance work over the long term.
5. **The open community is small.** The GitHub repository has about 104 stars and 57 forks. The free Community Edition can be up to 3 months behind the latest development version. In practice you depend on the Apperta Foundation or a paid support partner.
6. **The licence is AGPL v3.** If you change the code and offer it to others over a network, for example as a hosted service, you must publish your changes.
7. **Subspecialty coverage is uneven.** Cataract, glaucoma and medical retina are clearly well served. The documentation shows much less for paediatrics, strabismus, oculoplastics, cornea and refractive surgery.

## Where it fits

| Setting | Fit |
|---|---|
| A UK NHS eye department | Excellent. This is what it was designed for. |
| A large eye hospital elsewhere that has an IT team | Good, if you budget for adapting it to local forms, language and links to existing systems. |
| A small private practice | Weak on its own, because there is no scheduling or billing. |
| Research or teaching | Good: structured data, open code and the audit tools. |

## Sources

- [OpenEyes features in depth](https://openeyes.apperta.org/oedetail)
- [GitHub – appertafoundation/openeyes](https://github.com/appertafoundation/openeyes)
- [OpenEyes documentation](https://mintlify.wiki/appertafoundation/openeyes/introduction)
- [Bolton goes live with OpenEyes (Digital Health)](https://www.digitalhealth.net/2017/03/bolton-deploys-open-eyes-open-source-software/)
- [Northern Care Alliance go-live](https://openeyes.apperta.org/news/2020/07/28/nca.html)
- [NHS glaucoma virtual clinic playbook](https://transform.england.nhs.uk/key-tools-and-info/digital-playbooks/eye-care-digital-playbook/setting-up-a-virtual-evaluation-clinic-for-follow-up-glaucoma-patients)
- [Eye News – OpenEyes Community Edition review](https://www.eyenews.uk.com/reviews/tech-reviews/post/openeyes-community-edition)
