# judaro — קטלוג מלא: 14 תחומים, 282 סקילים

נסרק דרך חיבור judaro פעיל ב-claude.ai. כל 14 התחומים `accessible: true`, אפס סקילים נעולים.
מקור הנתונים: `list_domains` + `list_skills(domain=…)` מול השרת החי.

| # | תחום | id | סקילים |
|---|---|---|---|
| 1 | נזיקין ★ | `tort` | 11 |
| 2 | ליטיגציה ★ | `lit` | 16 |
| 3 | חדלות פירעון | `insol` | 22 |
| 4 | משפחה ומעמד אישי | `fam` | 23 |
| 5 | ייפוי כוח מתמשך | `poa` | 20 |
| 6 | דיני עבודה (GC) | `labor` | 15 |
| 7 | תחרות והגבלים | `comp` | 17 |
| 8 | מכרזים (GC) | `tenders` | 7 |
| 9 | מיסוי מקרקעין | `landtax` | 24 |
| 10 | עסקאות מקרקעין | `landtx` | 24 |
| 11 | התחדשות עירונית | `urban` | 20 |
| 12 | תאגידי | `corp` | 23 |
| 13 | ירושה וצוואות | `wills` | 25 |
| 14 | פרטיות והגנת מידע | `priv` | 35 |
| | **סה"כ** | | **282** |

`landtax`, `landtx`, `urban` משתייכים לאוסף `real-estate`.

**מבנה אחיד בכל תחום:** `intake-*` → `case_brief.md` | `checklist-*` | `wrap-*` (ניסוח) | `caselaw-lookup` אחד | `faq-query` אחד.
חריגים: ל-`labor` ול-`tenders` אין `faq-query`; ל-`comp` אין `checklist-intake` נפרד.

**אזהרת אימות:** כל ציטוט פסיקה וכל נתון מספרי בסקילים מתויג **[לאמת]** — אין להסתמך בלי אימות במאגר חי (נבו / תקדין / פדאור). אימות בעליון: supremedecisions.court.gov.il — ידנית בלבד.

---

## 1. tort — נזיקין (11) ★

| id | מה עושה | טריגר |
|---|---|---|
| `tort/skill/intake-tort` | קליטה + סיווג משטר (פלת"ד/רגיל/רפואי/מוצר/חי/מעביד) → case_brief + timeline | "פתח תיק נזיקין" |
| `tort/skill/liability-analysis` | 4 רכיבי חבות + הגנות צפויות → liability_analysis.md | "נתח חבות", "מה הסיכוי" |
| `tort/skill/damage-calculator` | תחשיב לפי ראשי נזק → damages_calc.md. דורש case_brief + חוו"ד | "תחשיב נזק", "כמה שווה התיק" |
| `tort/skill/nii-offset-calculator` | ניכוי גמלאות מל"ל, היוון, מינימום 25% כשהמדינה נתבעת | "ניכוי מל"ל", "תחשב את ה-25%" |
| `tort/skill/plt-pain-calculator` | כאב וסבל פלת"ד לפי תקנות התשל"ו (2‰×אשפוז + 1%×נכות, הפחתת גיל) | "כאב וסבל פלת"ד" |
| `tort/skill/road-accident-classification` | עץ החלטה: תאונת דרכים לפי פלת"ד או רשלנות | "פלת"ד או רגיל" |
| `tort/skill/medical-records-review` | ציר זמן רפואי, סתירות, רישומי מל"ל מקדמיים, שאלות למומחה | "תקרא תיק רפואי" |
| `tort/skill/expert-opinion-review` | 4 צירים: פורמלי / תוכן / התאמה / נקודות תקיפה | "בדוק את חוו"ד הצד שכנגד" |
| `tort/skill/settlement-evaluator` | 6 צירי הערכת פשרה → settlement_eval.md | "האם לקבל פשרה" |
| `tort/skill/caselaw-lookup` | חובת זהירות, אסכולה, הסכמה מדעת, ניכויי מל"ל, פלת"ד, חבות מוצר | "פסיקה על..." |
| `tort/skill/faq-query` | משטר, חבות, רשלנות רפואית, היוון, התיישנות, תשלום תכוף | "כמה זמן להתיישנות" |

## 2. lit — ליטיגציה (16) ★

| id | מה עושה | טריגר |
|---|---|---|
| `lit/skill/intake-litigation` | קליטה + סיווג תחום מהותי → case_brief + timeline + דדליינים | "פתח תיק ליטיגציה" |
| `lit/skill/pleading-drafter` | כתב תביעה docx. `--type` tort/contract/property/defamation/consumer | "נסח כתב תביעה" |
| `lit/skill/defense-drafter` | כתב הגנה — מטריצת השוואה, טענות מקדמיות, תשובה פסקה-פסקה, צד ג' | "הוגשה נגדנו תביעה" |
| `lit/skill/motion-drafter` | בקשות ביניים: סעד זמני, סילוק על הסף, גילוי, שאלונים, תיקון, ארכה | "נסח בקשה" |
| `lit/skill/evidence-matrix` | טבלת פלוגתא→ראיה→משקל→סתירות→מי חוקר (כלי בסיס לשאר) | "מטריצת ראיות" |
| `lit/skill/case-weakness-analysis` | חולשות שלי ושל היריב + אסטרטגיה לכל אחת | "איפה אנחנו פגיעים" |
| `lit/skill/pretrial-summary` | תכנית קדם משפט: פלוגתאות, עדים, מוצגים, עמדה לפשרה | "תכין אותי לקדם מסכם" |
| `lit/skill/direct-exam-prep` | חקירה ראשית: מטרה / תשובה צפויה / סיכון / המשך לכל שאלה | "הכן חקירה ראשית של" |
| `lit/skill/cross-exam-prep` | חקירה נגדית — שאלות סגורות מסתירות, בנייה מהרך לשיא | "הכן חקירה נגדית של" |
| `lit/skill/expert-cross-prep` | חקירת מומחה: ידע, אסכולה, רישומים, ספרות. דורש חוו"ד + קו"ח | "תקוף את חוות הדעת" |
| `lit/skill/witness-simulation` | מגלם עד לתרגול אינטראקטיבי | "תגלם את [עד]" |
| `lit/skill/summations-drafter` | סיכומים בע"פ (ברירת מחדל תקסד"א 2018) או בכתב | "נסח סיכומים" |
| `lit/skill/post-judgment` | ערעור (45 יום) / רע"א (30 יום) / ביצוע בהוצל"פ | "פסק יצא — מה הלאה" |
| `lit/skill/judge-profile` | פרופיל שופט לפני ובמהלך הדיון | "מי [שופט]" |
| `lit/skill/caselaw-lookup` | נזיקין, חוזים, מקרקעין, לשה"ר, סד"א, ראיות | "תקדים ל..." |
| `lit/skill/faq-query` | התיישנות, סמכות, הרחבת חזית, סעדים זמניים, גילוי, ערעור | "מה זה הרחבת חזית" |

## 3. insol — חדלות פירעון (22)

| id | מה עושה |
|---|---|
| `insol/skill/intake-insolvency` | אינטייק 10 חלקים (כולל "חוקר פרטי דמיוני") → case_brief |
| `insol/skill/checklist-intake` | אותו אינטייק כצ'קליסט (04_CHECKLISTS #1) |
| `insol/skill/checklist-track-choice` | הסדר פרטי / הוצל"פ / חלק י' (318) / בקשת יחיד |
| `insol/skill/checklist-opening` | לפני טופס 5 לממונה |
| `insol/skill/checklist-interim` | תקופת ביניים 9-12 ח': דוחות דו-חודשיים, בירור |
| `insol/skill/checklist-rehab-hearing` | לקראת דיון שיקום (60 יום אחרי דוח 9 חודשים) |
| `insol/skill/checklist-pension` | 5 שכבות הגנה פנסיונית |
| `insol/skill/checklist-residence` | דירת מגורים: 48 חודשים, פדיון יחסי |
| `insol/skill/checklist-creditor-rep` | ייצוג נושה: 110 / 109(ב) |
| `insol/skill/checklist-trustee` | לנאמן: קבלת תיק, בירור, דוח 153 |
| `insol/skill/wrap-fee-agreement` | שכ"ט One-Shot, צד ג' משלם |
| `insol/skill/wrap-warning-letter` | התראה 110(א)(1), 45 יום |
| `insol/skill/wrap-creditor-petition` | בקשת נושה 110 / נושה עתידי 109(ב) |
| `insol/skill/wrap-debt-claim` | תביעת חוב מקוונת (מובטח / קדימה / רגיל) |
| `insol/skill/wrap-payment-reduction` | הפחתת תשלום 156(ה) |
| `insol/skill/wrap-business-permit` | היתר ניהול עסק 157 |
| `insol/skill/wrap-creditor-settlement` | הסדר חוב חלק י' (318) לבעלי רישיון |
| `insol/skill/wrap-avoidance-petition` | ביטול הענקה 220 (קרוב 2/4 שנים, צד ג' 7) |
| `insol/skill/wrap-trustee-response` | תגובה לדוח נאמן 153 |
| `insol/skill/wrap-privilege-response` | חיסיון עו"ד-לקוח (סלביון / וקסברג) |
| `insol/skill/caselaw-lookup` | מבחני חדל"פ, פנסיה, דירה, הענקות, רפורמת 2018 |
| `insol/skill/faq-query` | שכ"ט, יציאה מהארץ, דמי מחיה, רשות המסים |

## 4. fam — משפחה ומעמד אישי (23)

| id | מה עושה |
|---|---|
| `fam/skill/intake-family` | סיווג: prenup / postnup / ידועים בציבור / divorce / property / enforcement / opening → case_brief |
| `fam/skill/checklist-intake-new-client` | לפני / בתוך / אחרי פגישה ראשונה |
| `fam/skill/checklist-pre-drafting` | לפני כתיבת הסכם ממון |
| `fam/skill/checklist-pre-prenup-approval` | מסלול אישור: נוטריון טופס 12 / בימ"ש |
| `fam/skill/checklist-pre-divorce-signing` | לפני חתימת הסכם גירושין |
| `fam/skill/checklist-tax-planning-4a` | סעיף 4א, חזקת התא המשפחתי, מס שבח אגב גירושין |
| `fam/skill/checklist-enforcement-opening` | אכיפה (סעיף 7) / פתיחת הסכם |
| `fam/skill/checklist-malpractice-redflags` | נורות רשלנות מקצועית רוחביות |
| `fam/skill/wrap-prenup-full` | הסכם ממון מלא 15 סעיפים |
| `fam/skill/wrap-prenup-property-clause` | הסכם ממון לנכס ספציפי |
| `fam/skill/wrap-prenup-residence-clause` | דירה של צד אחד, "המגורים לא יוצרים שיתוף" |
| `fam/skill/wrap-prenup-options-clause` | אופציות / מניות — בע"מ 7482/18 |
| `fam/skill/wrap-prenup-kera-date` | מועד קרע משולש + חלופת בגידה |
| `fam/skill/wrap-cohabitation-agreement` | הסכם ידועים בציבור 6 סעיפים |
| `fam/skill/wrap-divorce-agreement` | הסכם גירושין מקיף 13 סעיפים |
| `fam/skill/wrap-divorce-property-division` | דירה (3 חלופות), בנקים, פנסיה (תשע"ד-2014) |
| `fam/skill/wrap-divorce-custody-schedule` | הסדרי שהות, תקנות 2021, 919/15 |
| `fam/skill/wrap-child-maintenance-clause` | מזונות ילדים 919/15 + הוצאות חריגות |
| `fam/skill/wrap-mezonot-style-clause` | תניית "כדין מזונות" |
| `fam/skill/wrap-disclosure-7525-clause` | סנקציה 75/25 לאי-גילוי |
| `fam/skill/wrap-property-asset-affidavit` | תצהיר רכוש 13 קטגוריות |
| `fam/skill/caselaw-lookup` | שיתוף ספציפי, תא משפחתי, 7482/18, 919/15 |
| `fam/skill/faq-query` | 40 שו"ת ב-10 חלקים |

## 5. poa — ייפוי כוח מתמשך (20)

| id | מה עושה |
|---|---|
| `poa/skill/intake-poa` | סיווג: קלאסי / פסיכיאטרי / ידועים בציבור / ערירי + דגלים |
| `poa/skill/checklist-first-meeting` | פגישה ראשונה + פגישה נפרדת (חובה) |
| `poa/skill/checklist-red-flags` | "שריפת קלפים" — מתי לסרב |
| `poa/skill/checklist-form-filling` | טופס דיגיטלי "כשרות משפטית אונליין" |
| `poa/skill/checklist-deposit` | הדפסה, חתימה, הפקדה |
| `poa/skill/checklist-entry-into-force` | חוו"ד רפואית לפני הגשה, הגשה חוזרת |
| `poa/skill/checklist-revocation` | ביטול 32כט — רך קודם, בימ"ש לא אפ"כ |
| `poa/skill/checklist-malpractice-defense` | תיק פנימי הגנתי |
| `poa/skill/wrap-advance-directives` | הנחיות מקדימות 8 אזורים |
| `poa/skill/wrap-bank-clauses` | מבנה חתימות, סף כספי, דיגיטלי |
| `poa/skill/wrap-realestate-clauses` | מכירה / השכרה / שעבוד, סדר עדיפויות, תיאום צוואה |
| `poa/skill/wrap-effect-conditions` | כניסה לתוקף ופקיעה, סוג מומחה |
| `poa/skill/wrap-notified-parties` | מיודעים — חלופה ל"שריפת אחים" |
| `poa/skill/wrap-ulysses-clauses` | סעיפי יוליסס פסיכיאטריים |
| `poa/skill/wrap-cohabitants` | ידועים בציבור — הגנה על מגורים |
| `poa/skill/wrap-defensive-declarations` | הצהרות שומר סף |
| `poa/skill/wrap-authority-notices` | הודעה לבנק / קופ"ח |
| `poa/skill/wrap-revocation-petition` | בקשת ביטול 32כט + תצהירים (מבחני מרום) |
| `poa/skill/caselaw-lookup` | שומר סף, חיסיון, השפעה בלתי הוגנת, בנקים |
| `poa/skill/faq-query` | ילד בחו"ל, ניגוד עניינים, back-to-back עם צוואה |

## 6. labor — דיני עבודה (15) — ברירת מחדל צד מעסיק קשיחה

| id | מה עושה |
|---|---|
| `labor/skill/intake-matter` | קליטה מזווית הארגון → case_brief (סכמת ARGUS) |
| `labor/skill/advisory-memo` | מזכר להנהלה / HR, החלטה-תחילה |
| `labor/skill/termination-risk-check` | מטריצת סיכון פיטורים 🔴🟠🟡🟢 |
| `labor/skill/severance-calculator` | חשיפת פיצויים, סעיף 14, השלמת חסר |
| `labor/skill/constructive-dismissal-risk` | התפטרות בדין מפוטר ס' 6/7/8/11 |
| `labor/skill/protected-pregnancy-leave-clearance` | היתר ממונה — חוק עבודת נשים |
| `labor/skill/discrimination-exposure-audit` | ביקורת אפליה רוחבית, ייצוגית |
| `labor/skill/employee-monitoring-advisory` | מצלמות, ניטור מייל, איכון, פוליגרף, AI |
| `labor/skill/harassment-investigation` | בירור הטרדה / התעמרות מצד הארגון |
| `labor/skill/cash-payment-compliance-check` | חוק צמצום מזומן בשכר |
| `labor/skill/officer-criminal-exposure-screening` | חוק הגברת האכיפה — נושאי משרה, מזמין שירות |
| `labor/skill/policy-drafter` | תקנונים ונהלים |
| `labor/skill/demand-response` | מענה למכתב דרישה + מזכר חשיפה |
| `labor/skill/labor-court-defense` | כתב הגנה לבית הדין (תקנות תשנ"ב) |
| `labor/skill/caselaw-lookup` | עליון > ארצי > אזורי → caselaw_brief.md |

## 7. comp — תחרות והגבלים (17)

| id | מה עושה |
|---|---|
| `comp/skill/intake-competition` | 4 עמודי תווך → case_brief + timeline |
| `comp/skill/analyzer-market-definition` | שוק רלוונטי, SSNIP |
| `comp/skill/analyzer-restrictive-arrangement` | הסדר כובל ס' 2, חריגי 3, פטורים |
| `comp/skill/analyzer-monopoly-abuse` | ניצול לרעה 29-29א |
| `comp/skill/checklist-monopoly-self-assessment` | מונופולין / כוח שוק משמעותי (ס' 26) |
| `comp/skill/checklist-merger-filing` | חובת דיווח 17, HHI, תקופת בדיקה |
| `comp/skill/checklist-compliance-program` | תוכנית ציות |
| `comp/skill/checklist-dawn-raid-readiness` | חיפוש פתע, First-Hour |
| `comp/skill/checklist-leniency-application` | חסינות / הקלה, marker |
| `comp/skill/wrap-merger-notification` | הודעת מיזוג |
| `comp/skill/wrap-block-exemption-application` | פטור-סוג / הערכה עצמית (גילוי דעת 1/18) |
| `comp/skill/wrap-competition-clause` | RPM, non-compete, בלעדיות |
| `comp/skill/wrap-leniency-request` | בקשת חסינות |
| `comp/skill/wrap-consent-order` | צו מוסכם 50ב [לאמת] |
| `comp/skill/wrap-position-paper` | נייר עמדה לגילוי דעת / שימוע |
| `comp/skill/caselaw-lookup` | שטראוס-ויילר, מגנזי, יוניפארם-סנופי, קוטג' + 538 פס"ד |
| `comp/skill/faq-query` | הסדר כובל, RPM, ספי מיזוג, leniency |

## 8. tenders — מכרזים (7) — הצד נקבע בפרופיל

| id | מה עושה |
|---|---|
| `tenders/skill/intake-matter` | משטר (ממשלתי / מקומי / ביטחון), צד, מסגור → matter_brief |
| `tenders/skill/advisory-memo` | מזכר BLUF לוועדת מכרזים / מציע |
| `tenders/skill/checklist-bidding` | מציע לפני הגשה — תנאי סף, ערבות, תצהירים |
| `tenders/skill/checklist-procurement` | עורך מכרז — אומדן (17), סף (6), אמות מידה (22) |
| `tenders/skill/wrap-bid-evaluation` | פרוטוקול ועדה + הערכת הצעות |
| `tenders/skill/wrap-petition` | עתירה מינהלית / מענה, שעון 45 יום, סעד זמני |
| `tenders/skill/caselaw-lookup` | עליון / בג"ץ > מינהלי → caselaw_brief |

## 9. landtax — מיסוי מקרקעין (24)

| id | מה עושה |
|---|---|
| `landtax/skill/intake-land-tax` | מכר / רכישה / מתנה / ירושה / קומבינציה / תמ"א → case_brief |
| `landtax/skill/checklist-before-drafting` | איזה פטור / מסלול |
| `landtax/skill/checklist-during-drafting` | סעיפי מס בחוזה |
| `landtax/skill/checklist-before-reporting` | דיווח 30 יום (73), תשלום 60 |
| `landtax/skill/checklist-after-assessment` | השגה 30 יום, פריסה, מס יסף |
| `landtax/skill/checklist-full-workflow` | מקצה לקצה: 49ב(2) / גרייס / מתנה |
| `landtax/skill/checklist-niche-situations` | מתנה אנכית (שומרת), קומבינציה 25%, מס רכוש, אחרי גירושין |
| `landtax/skill/wrap-intake-questionnaire-seller` | שאלון מוכר |
| `landtax/skill/wrap-intake-questionnaire-buyer` | שאלון רוכש |
| `landtax/skill/wrap-clause-shevach-49b2` | סעיף שבח פטור דירה יחידה |
| `landtax/skill/wrap-clause-shevach-linear` | לינארי מוטב 48א(ב2) |
| `landtax/skill/wrap-clause-rechisha-single-unit` | מס רכישה 9(ג), גרייס 18/12 |
| `landtax/skill/wrap-clause-tama-49lo1` | תמ"א 49לו1, פטור 49לג1 |
| `landtax/skill/wrap-clause-combination-25` | הוראת שעה 25% (הסדרים 2023) |
| `landtax/skill/wrap-clause-property-tax` | מס רכוש מחודש, 54א |
| `landtax/skill/wrap-request-exemption-49b2` | בקשת פטור 49ב(2) |
| `landtax/skill/wrap-request-linear-48a-b2` | בקשת לינארי + הקטנת מקדמה 15(ב) |
| `landtax/skill/wrap-request-shevach-spread` | פריסה 91(ה) |
| `landtax/skill/wrap-request-ruling-estate` | רולינג חלוקת עיזבון 5(ג)(4), 49ג(3) |
| `landtax/skill/wrap-email-warning-gift` | אזהרת צינון 49ו |
| `landtax/skill/wrap-email-warning-grace` | אזהרת גרייס לרוכש |
| `landtax/skill/wrap-email-warning-yasaf` | מס יסף 121ב |
| `landtax/skill/caselaw-lookup` | שומרת, פרייטיג, רייך, לילי שמשון, הולצר |
| `landtax/skill/faq-query` | יסף, פריסה, גרייס, צינון, תושב חוץ |

## 10. landtx — עסקאות מקרקעין (24)

| id | מה עושה |
|---|---|
| `landtx/skill/intake-land-transaction` | סוג עסקה, זיהוי מוכר, נסח, נורות → case_brief |
| `landtx/skill/checklist-first-meeting` | מוכר 20 פריטים / קונה +8 |
| `landtx/skill/checklist-red-flags` | 9 נורות (צ'ק 3) |
| `landtx/skill/checklist-pre-signature-dd` | לפי סוג: בית משותף / חברה משכנת / רמ"י / קבלן / נחלה |
| `landtx/skill/checklist-signing-day` | מעמד חתימה (צ'ק 9, 13) |
| `landtx/skill/checklist-post-signing` | אחרי חתימה (צ'ק 10/11) |
| `landtx/skill/checklist-tax-reporting` | טופס 7000 / 7002 / 7009, 30 יום |
| `landtx/skill/checklist-rami-transfer` | מסמכי רמ"י לרישום (צ'ק 21) |
| `landtx/skill/checklist-case-closing` | סגירת תיק (צ'ק 22) |
| `landtx/skill/wrap-fee-agreement` | שכ"ט עם החרגות ורשת ביטחון |
| `landtx/skill/wrap-recitals-property-state` | "הואיל" — בית משותף / רמ"י / חברה משכנת |
| `landtx/skill/wrap-seller-declarations` | הצהרות מוכר 14 תת-סעיפים (תבנית 31) |
| `landtx/skill/wrap-remedies-clause` | תרופות והפרה + תיקון "הפצצה המתקתקת" |
| `landtx/skill/wrap-mortgage-clause` | סעיף משכנתה 8 תתי-סעיפים |
| `landtx/skill/wrap-payoff-letter` | מכתב כוונות מבנק |
| `landtx/skill/wrap-buyer-counsel-undertaking` | התחייבות עו"ד קונה לבנק (3 שורות) |
| `landtx/skill/wrap-handover-protocol` | פרוטוקול מסירה |
| `landtx/skill/wrap-rami-transfer-clause` | סעיף מסמכי העברה רמ"י (7 מסמכים) |
| `landtx/skill/wrap-lease-transfer-deed` | כתב העברת חכירה |
| `landtx/skill/wrap-nahala-suspensive-condition` | תנאי מתלה נחלה — אישור אגודה |
| `landtx/skill/wrap-nahala-chattel-agreement` | הסכם מטלטלין נחלה |
| `landtx/skill/wrap-closing-letter` | מכתב סיום טיפול |
| `landtx/skill/caselaw-lookup` | וייזמן-קלימי, גנץ, שטיינמץ, קל-בניין, חפציבה |
| `landtx/skill/faq-query` | FAQ מהשדה |

## 11. urban — התחדשות עירונית (20)

| id | מה עושה |
|---|---|
| `urban/skill/intake-urban-renewal` | מסלול 38/1 / 38/2 / פינוי-בינוי → case_brief |
| `urban/skill/checklist-initial-inquiry` | היתכנות, 80% חתימות לכתב מינוי |
| `urban/skill/checklist-developer-vetting` | איתנות יזם, כרית 40% |
| `urban/skill/checklist-contract-obligations` | סעיפי חובה בהסכם דיירים-יזם |
| `urban/skill/checklist-elderly-mapping` | מיפוי קשישים 70+ / 75+ |
| `urban/skill/checklist-objector` | תביעת סרבן — מפקח / מחוזי |
| `urban/skill/checklist-pre-eviction` | לפני הודעת פינוי |
| `urban/skill/checklist-handover-and-registration` | מסירה, רישום בית משותף |
| `urban/skill/wrap-representation-mandate` | כתב מינוי נציגות + רוב |
| `urban/skill/wrap-fee-agreement` | שכ"ט דיירים, פעימות, מימון יזם |
| `urban/skill/wrap-suspensive-conditions` | 5 תנאים מתלים (פרק ג') |
| `urban/skill/wrap-guarantees-package` | 5 שכבות ערבויות |
| `urban/skill/wrap-powers-of-attorney` | 5 ייפויי כוח מפוצלים + נאמן |
| `urban/skill/wrap-elderly-annex` | נספח קשישים, 49כ"א / 49כ"ב |
| `urban/skill/wrap-tax-questionnaire` | שאלון מיסוי דייר |
| `urban/skill/wrap-betterment-levy-refund` | החזר היטל השבחה 19(ג) |
| `urban/skill/wrap-eviction-notice` | הודעת פינוי — 7 תנאי 13.1 |
| `urban/skill/wrap-dispute-resolution` | גישבור / 3 בוררים |
| `urban/skill/caselaw-lookup` | סרבן, שוויון, היטל השבחה, ערבויות |
| `urban/skill/faq-query` | 38/1 מול 38/2, סרבן, ערבויות, קשישים |

## 12. corp — תאגידי (23)

| id | מה עושה |
|---|---|
| `corp/skill/intake-corporate` | הקמה / השקעה / עסקת מניות / מכירת פעילות / תחזוקה / פירוק → case_brief + Cap Table ראשוני |
| `corp/skill/checklist-intake` | 10 השאלות המנחות + אזהרות מס Day 1 |
| `corp/skill/checklist-incorporation` | הקמת חברה: מבנה, שם, ע.נ., רשם, בנק, הלוואת בעלים, ישיבה ראשונה |
| `corp/skill/checklist-due-diligence` | DD בשלוש שכבות — Quick & Dirty / משפטית / פיננסית + טכנולוגית |
| `corp/skill/checklist-sha-drafting` | שבעת פרקי החובה ב-SHA + בחירת Bumby |
| `corp/skill/checklist-closing` | Closing Package: פרוטוקולים, שטרות, מרשם, CEO Cert, Legal Opinion |
| `corp/skill/wrap-articles` | תקנון RTL בשלוש רמות (קצר / בינוני / ארוך) |
| `corp/skill/wrap-sha` | SHA / הסכם מייסדים — קצר / בינוני (+Bumby, 6-7 וטואים) / ארוך |
| `corp/skill/wrap-shareholder-loan` | הלוואת בעלים — חובה Day 1, אחרת ס' 3(ט1) |
| `corp/skill/wrap-safe` | SAFE עם Valuation Cap ו-Discount, מודל YC מותאם ישראל |
| `corp/skill/wrap-share-issuance` | הסכם הקצאה — Plain Vanilla או מורחב |
| `corp/skill/wrap-stock-purchase` | SPA — קצר או Full Form (מצגים, שיפוי, תנאים מתלים) |
| `corp/skill/wrap-share-transfer` | שטר העברת מניות — בעלות רק לאחר עדכון מרשם |
| `corp/skill/wrap-asset-deal` | מכירת פעילות — פחת מוניטין 10%, העברת עובדים, אי-תחרות |
| `corp/skill/wrap-term-sheet` | Term Sheet / MOU / LOI — מחייב/לא, No-Shop, שיפוט |
| `corp/skill/wrap-joinder` | כתב הצטרפות ל-SHA קיים |
| `corp/skill/wrap-board-resolution` | פרוטוקול דירקטוריון — פיזי / ועידה / בכתב |
| `corp/skill/wrap-ceo-certificate` | תעודת מנכ"ל לפער Signing→Closing |
| `corp/skill/wrap-legal-opinion` | חוות דעת עו"ד ל-Closing Package |
| `corp/skill/wrap-non-compete` | אי-תחרות ביציאת בעל מניות / מכירת פעילות |
| `corp/skill/wrap-summary-email` | מייל סיכום Day 1 + אזהרות מס + תחזוקה שנתית |
| `corp/skill/caselaw-lookup` | קיפוח, הרמת מסך, חובת אמון, אורליינד, בית חוסן, איצ'ר |
| `corp/skill/faq-query` | Vesting, וטו, RoFR/RoFO/Tag/Drag/Bumby, דילול, SAFE, ס' 102 |

## 13. wills — ירושה וצוואות (25)

| id | מה עושה |
|---|---|
| `wills/skill/intake-inheritance` | סיווג: עריכת צוואה / עיזבון / התנגדות / נאמנות / חלוקה / הסתלקות → case_brief |
| `wills/skill/checklist-intake-meeting` | סדר יום לפגישה ראשונה (5 שלבים, ~90 דק') |
| `wills/skill/checklist-capacity-assessment` | התרשמות מכשרות + דגלים אדומים → להמשיך / לדחות / חוו"ד רפואית |
| `wills/skill/checklist-will-drafting` | עריכת צוואה מקצה לקצה: נכסים, יורשים, מס, ס' 20, מלכודות |
| `wills/skill/checklist-signing-ceremony` | מעמד החתימה — 8 צעדים לפי ס' 20, תיעוד מרבי |
| `wills/skill/checklist-post-death-3days` | שלושת הימים הראשונים אחרי פטירה |
| `wills/skill/checklist-estate-management` | ניהול עיזבון: איזון משאבים, מנהל עיזבון, חלוקה, זכות קדימה, טאבו |
| `wills/skill/checklist-will-objection` | ארבעת הצירים + סינון "סיפור לא הגיוני" |
| `wills/skill/wrap-will-single-witnessed` | צוואת יחיד בעדים (ס' 20) — תבנית מאסטר, ~85% מהתיקים |
| `wills/skill/wrap-will-mutual` | צוואה הדדית (ס' 8א) + חוזה הסתמכות + סנקציה |
| `wills/skill/wrap-special-clauses` | יורש-אחר-יורש (42), יורש-במקום-יורש (41), מושע 49ג |
| `wills/skill/wrap-charge-clause` | חיוב יורש ס' 45 — חיובי / שלילי / ביצוע פעולה |
| `wills/skill/wrap-trust-clause` | נאמנות בצוואה: קטין, חסוי, בזבזן, נכדים, פרוטקטור |
| `wills/skill/wrap-digital-assets` | נכסים דיגיטליים — ענן, קריפטו, פייסבוק, פיצול סיסמה |
| `wills/skill/wrap-notary-affidavit` | הצהרה לפני חתימה + אישור נוטריון מורחב (ס' 22) |
| `wills/skill/wrap-tax-rejection-protocol` | פרוטוקול הצעות מס שנדחו — מסמך זהב נגד רשלנות |
| `wills/skill/wrap-probate-order-application` | צו ירושה / צו קיום צוואה לרשם הירושה |
| `wills/skill/wrap-estate-administrator-motion` | בקשה למינוי מנהל עיזבון + תכנית ניהול |
| `wills/skill/wrap-estate-distribution-agreement` | הסכם חלוקה (110) + עוגן מס 5(ג)(4) |
| `wills/skill/wrap-renunciation` | הסתלקות ס' 6/6א/7 + הוראת שעה חרבות-ברזל |
| `wills/skill/wrap-heirs-pre-death-agreement` | הסכם בין יורשים בחיי המצווה — ס' 8, הלכת הנדל |
| `wills/skill/wrap-will-objection` | כתב התנגדות — הלכת החוטים השזורים |
| `wills/skill/wrap-fee-agreement` | שכ"ט צוואה / עיזבון / התנגדות |
| `wills/skill/caselaw-lookup` | משפחה > מחוזי בערעור > עליון → caselaw_brief |
| `wills/skill/faq-query` | כשרות, הסתלקות, חלוקה בעין, נאמנות, נכסים דיגיטליים, שכ"ט |

## 14. priv — פרטיות והגנת מידע (35)

| id | מה עושה |
|---|---|
| `priv/skill/intake-privacy` | ייעוץ / DPIA / אירוע / DSAR / אכיפה / חוו"ד מקדמית / מאגר חדש → intake |
| `priv/skill/checklist-dpo-tasks-master` | מאסטר DPO — 14 גליונות / 10 תחומי ציות (כלי הרשות) |
| `priv/skill/checklist-dpo-appointment` | האם חלה חובת DPO, כשירות מועמד, תנאי העסקה, דיווח |
| `priv/skill/checklist-board-privacy` | אחריות דירקטוריון — תקנות 2017 + תיקון 13 |
| `priv/skill/checklist-pia` | תסקיר — מה לאסוף, להחליט ולתעד ב-7 השלבים |
| `priv/skill/checklist-data-minimization` | צמצום: איסוף / אחסון / גישה / שיתוף / שמירה |
| `priv/skill/checklist-data-lifecycle` | DLM תפעולי ל-DPO לכל שלב |
| `priv/skill/checklist-incident-response` | 4 חלונות זמן: ≤2ש' / ≤24ש' / ≤72ש' / ≤30 יום |
| `priv/skill/checklist-risk-survey` | סקר סיכונים + מבדק חדירות (תקנה 5) |
| `priv/skill/checklist-logs-takana-10d` | לוגים 24 חודשים, ניטור, גישה מבוקרת |
| `priv/skill/checklist-takana-15` | מיקור חוץ: בחירת ספק, התקשרות, מעקב, סיום |
| `priv/skill/checklist-cloud-migration` | ענן — תקנה 15 + תקנה 2(4) + רמת אבטחה |
| `priv/skill/checklist-cross-border-transfer` | בדיקה מקדמית לפני העברה לחו"ל (תקנה 2(4)) |
| `priv/skill/checklist-oss-security` | סיכוני קוד פתוח |
| `priv/skill/checklist-emergency-privacy` | פרטיות בחירום — מלחמה / מגפה / אסון (ס' 23) |
| `priv/skill/checklist-enforcement-track-triage` | ניתוב: בירור מנהלי מול חקירה פלילית (ס' 23טז) |
| `priv/skill/wrap-privacy-notice` | הודעת פרטיות לאתר / אפליקציה (ס' 11 אחרי תיקון 13) |
| `priv/skill/wrap-dpo-appointment` | כתב מינוי DPO (17ב1-3) — עצמאות, גישה להנהלה |
| `priv/skill/wrap-dpo-compliance-tracker` | דו"ח ציות תקופתי לדירקטוריון — 10 תחומים |
| `priv/skill/wrap-pia` | תסקיר השפעה מלא — 7 שלבים לפי מדריך הרשות |
| `priv/skill/wrap-data-lifecycle-policy` | מדיניות מחזור חיי מידע — 5 שלבים |
| `priv/skill/wrap-breach-notification` | הודעת אירוע לרשות ולנושאי מידע (תקנה 11) |
| `priv/skill/wrap-outsourcing-dpa` | DPA לפי תקנה 15 |
| `priv/skill/wrap-cross-border-transfer` | סעיף / נספח העברה לחו"ל — 3 חלופות |
| `priv/skill/wrap-database-transfer` | העברת בעלות במאגר (הנחיה 2/2024) — M&A, מיזוג, פירוק |
| `priv/skill/wrap-preliminary-opinion-request` | בקשת חוו"ד מקדמית מהרשות (17ט2), מענה 60 יום |
| `priv/skill/wrap-dsar-recordings` | מענה לבקשת עיון בהקלטות — חישוף צד ג', טשטוש |
| `priv/skill/wrap-workplace-camera-policy` | מצלמות בעבודה — הנחיה 3/17 + עדכון 2025 |
| `priv/skill/wrap-employee-location-tracking` | איכון עובדים — רכב חברה מול פרטי, שעות מנוחה |
| `priv/skill/wrap-remote-work-monitoring` | מעקב בעבודה מרחוק — מסך, מקלדת, Zoom/Teams |
| `priv/skill/wrap-biometric-attendance` | ביומטריה לנוכחות — חלופות, הסכמה, אחסון תבנית |
| `priv/skill/wrap-medical-nda-hiring` | ויתור סודיות רפואית בקבלה לעבודה |
| `priv/skill/wrap-ai-pets-assessment` | PETs במערכת AI (מסמך 24 + הנחיית AI אפריל 2025) |
| `priv/skill/caselaw-lookup` | pinecone-israelaw אם מחובר + אינדקס פנימי |
| `priv/skill/faq-query` | חוק הגנת הפרטיות, תיקון 13, תקנות 2017, גילויי דעת |

---

## הערות טכניות

- `get_skill(id=...)` — הפרמטר הוא `id`, לא `skill_id`.
- כל skill מפנה לפלייבוקים של התחום: `<domain>/playbook/...` (03_TEMPLATES, 04_CHECKLISTS, 06_CASELAW, 07_FAQ). לאחר `get_skill` יש לעקוב אחרי הוראות ה-skill ולקרוא את המשאבים שהוא מציין.
- `get_playbook` / `get_knowledge` / `get_reference` מחזירים את המסמך **כולו** כברירת מחדל. הקשר משפטי נפרש על פני העמוד — לקרוא במלואו ולצמצם עם `section=` רק כשידוע איזה חלק בדיוק דרוש.
- מסמך גדול מדי חוזר כפתיחה + קישור הורדה של המסמך המלא (`download_file`) — להוריד ולקרוא במלואו.
- סקילים של `tort` ו-`lit` מסמנים כל ציטוט פסיקה **[ידע מודל — לאמת]**. אימות בעליון: supremedecisions.court.gov.il — ידנית בלבד.
- אם כלי מחזיר שגיאה / forbidden / השרת לא זמין — לומר זאת מפורשות ולא לענות על שאלות משפטיות מידע המודל.
