---
title: Použití rozšíření Image Analyzer | Microsoft Docs
description: 'Tato rozšíření umožňují analyzovat obrázky kontaktních osob a položek a hledat atributy, abyste je mohli rychle přiřadit v Business Central.'
documentationcenter: ''
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'API, extension, Cognitive Services, image, computer vision, attribute, tag, recognition'
ms.date: 06/19/2017
ms.author: bholtorf
---

# <a name="the-image-analyzer-extension-for-microsoft-business-central"></a>Rozšíření Image Analyzer pro Microsoft Business Central
Rozšíření Image Analyzer využívá výkonnou analytiku obrázků poskytovanou rozhraním Computer Vision API pro Microsoft Cognitive Services k detekci atributů v obrázcích, které importujete pro položky a kontaktní osoby, takže je můžete snadno zkontrolovat a přiřadit. U zboží může být atributem to, zda je zboží stůl nebo auto a zda je červené nebo modré. U kontaktních osob může být atributem pohlaví nebo věk.

Image Analyzer navrhuje atributy založené na úrovni spolehlivosti a na značkách, které najde rozhraní API Computer Vision. Ve výchozím nastavení jsou navrhované atributy, pouze pokud je alespoň 80% jistota, že je atribut správný. V případě potřeby můžete nastavit další úroveň spolehlivosti. Chcete-li se dozvědět více o tom, jak se určují značky a úroveň spolehlivosti, přečtěte si [Computer Vision API](https://go.microsoft.com/fwlink/?linkid=851476).  

Image Analyzer je zdarma na [!INCLUDE [d365fin](includes/d365fin_md.md)], ale počet zboží, které můžete analyzovat během určitého časového období, je omezen. Ve výchozím nastavení můžete analyzovat 100 obrázků za měsíc.

Po povolení rozšíření se program Image Analyzer spustí při každém importu obrázku do zboží nebo kontaktní osoby. Okamžitě uvidíte atributy, úroveň spolehlivosti a podrobnosti. Následně se můžete rozhodnout, co chcete s každým atributem udělat. Pokud jste importovali obrázky před povolením rozšíření Image Analyzer, musíte přejít ke zboží nebo kontaktním kartám a zvolit akci **Analyzovat obrázek**.  

> [!NOTE]
>   Povolením tohoto rozšíření souhlasíte s tím, že společnost Microsoft může ukládat vaše data a používat je ke zlepšení služeb společnosti Microsoft, jako je například vylepšování rozhraní Computer Vision API. Abychom chránili vaše soukromí, podnikáme kroky k tomu, aby vaše data byla anonymní a aby byla v bezpečí. Vaše data nezveřejníme ani nenecháme ostatní je používat. Obrázek můžete z položky odebrat v [!INCLUDE [d365fin](includes/d365fin_md.md)], ale rozhraní API Computer Vision bude mít obrázek stále v identifikované podobě. Pro více informací navštivte[ Centrum zabezpečení Microsoft](https://go.microsoft.com/fwlink/?linkid=851463).

## <a name="requirements"></a>Požadavky
Existuje několik požadavků na obrázky:

* Formáty obrázků: JPEG, PNG, GIF, BMP  
* Maximální velikost souboru: Méně než 4 MB  
* Rozměry obrázku: Větší než 50 x 50 pixelů  

## <a name="blacklisting-suggested-attributes"></a>Seznam zakázaných atributů
Pokud analýza navrhuje atribut, který nechcete vidět, můžete tento atribut zakázat. Buďte však opatrní. Zakázané atributy se nenavrhují ani pro jiné položky či kontaktní osoby. Pokud nechcete aby byl zakázaný atribut i nadále zakázán, vyberte **Zakázané atributy** a poté smažte atribut ze seznamu.

## <a name="to-enable-image-analyzer"></a>Povolení Image Analyzer
Rozšíření Image Analyzer je integrováno do [!INCLUDE [d365fin](includes/d365fin_md.md)]. Stačí ji zapnout.

> [!NOTE]  
> Chcete-li povolit rozšíření Image Analyzer, musíte být administrátorem. Ujistěte se, že jste dostali oprávnění uživatele **SUPER**.

1. Chcete-li povolit rozšíření Image Analyzer, proveďte jednu z následujících akcí:

* Otevřete zboží nebo kontaktní kartu. Na oznamovací liště zvolte **Analyzovat obrázky** a postupujte podle pokynů v průvodci nastavením.  
* Zvolte ikonu ![Vyhledat stránku nebo sestavu](media/ui-search/search_small.png "Ikona Vyhledat stránku nebo sestavu"), zadejte **Připojení služeb** a pak vyberte **Nastavení analýzy obrazu**. Zaškrtněte políčko **Povolit Image Analyzer** a dokončete kroky uvedené v průvodci nastavením.  

> [!TIP]
>   Stránka **Nastavení analýzy obrazu** je také místem, kde můžete změnit stupeň důvěryhodnosti pro návrhy atributů. Například, pokud chcete vyžadovat větší míru důvěry, můžete zadat vyšší procento.

## <a name="to-analyze-an-image-of-an-item"></a>Analýza obrázku zboží
Následující kroky popisují, jak analyzovat obrázek, který byl importován před povolením rozšíření Image Analyzer.  

1. Zvolte ikonu ![Vyhledat stránku nebo sestavu](media/ui-search/search_small.png "Ikona Vyhledat stránku nebo sestavu"), zadejte **Zboží** a pak vyberte související odkaz.  
2. Zvolte zboží a poté zvolte akci **Analyzovat obrázek**.  
3. Na stránce **Atributy Image Analyzer** se zobrazují zjištěné atributy, úroveň spolehlivosti a další podrobnosti o atributu. Pomocí možnosti **Akce k provedení** určete, co chcete s atributem udělat.  

> [!TIP]
>   Název atributu můžete přidat do popisu zboží výběrem možnosti **Přidat do popisu zboží**. To může být užitečné například pro rychlé přidání podrobností.  

## <a name="to-analyze-a-picture-of-a-contact-person"></a>Analýza obrázku kontaktní osoby
Následující kroky popisují, jak analyzovat obrázek, který byl importován před povolením rozšíření Image Analyzer.  

1. Zvolte ikonu ![Vyhledat stránku nebo sestavu](media/ui-search/search_small.png "Ikona Vyhledat stránku nebo sestavu"), zadejte **Kontakty** a pak vyberte související odkaz.  
2. Zvolte kontaktní osobu a poté zvolte akci **Analyzovat obrázek**.  
3. V záložce s náhledem **Profil. dotazník** zkontrolujte návrhy a v případě potřeby proveďte opravy.  

## <a name="to-use-your-own-account-for-the-computer-vision-api"></a>Použití vlastního účtu pro rozhraní Computer Vision API
Můžete také použít svůj vlastní účet pro rozhraní Computer Vision API, například, pokud chcete analyzovat více obrázků, než povolujeme.  

1. Zvolte ikonu ![Vyhledat stránku nebo sestavu](media/ui-search/search_small.png "Ikona Vyhledat stránku nebo sestavu"), zadejte **Nastavení analýzy obrazu** a pak vyberte související odkaz.  
2. Zadejte **API URI** a **Kód rozhraní API**, který jste obdrželi pro API Computer Vision.  

> [!NOTE]
>   Pokud již neexistuje, musíte přidat **/analyzovat** na konci API URI. Například: ```https://cronus.api.cognitive.microsoft.com/vision/v1.0/analyze```.

## <a name="to-see-how-many-analyses-you-have-left-in-the-current-period"></a>Podívejte se, kolik analýz vám zbývá v aktuálním období
Můžete zobrazit počet provedených analýz a kolik jich můžete v aktuálním období udělat.  

1. Zvolte ikonu ![Vyhledat stránku nebo sestavu](media/ui-search/search_small.png "Ikona Vyhledat stránku nebo sestavu"), zadejte **Nastavení analýzy obrazu** a pak vyberte související odkaz.  
2. **Typ limitu**, **Mezní hodnota** a **Provedené analýzy** poskytují informace o použití.  

## <a name="to-stop-using-the-image-analyzer-extension"></a>Zrušení používání rozšíření Image Analyzer
1. Zvolte ikonu ![Vyhledat Stránku nebo Sestavu](media/ui-search/search_small.png "Ikona Vyhledat Stránku nebo Sestavu"), zadejte **Připojení služeb** a pak vyberte **Nastavení analýzy obrazu**.  
2. Zrušte zaškrtnutí políčka **Povolit Image Analyzer**.  

## <a name="see-also"></a>Viz také
[Práce s atributy zboží](inventory-how-work-item-attributes.md)  
[Přizpůsobení [!INCLUDE[d365fin](includes/d365fin_md.md)] pomocí rozšíření](ui-extensions.md)  
[Vítejte v [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
