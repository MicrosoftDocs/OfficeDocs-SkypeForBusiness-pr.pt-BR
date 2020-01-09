---
title: Migrar o Catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Em geral, o catálogo de endereços é migrado juntamente com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente herdado:'
ms.openlocfilehash: 8c8e66a8182890ee6e3673769ddc620bb04404c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990096"
---
# <a name="migrate-address-book"></a><span data-ttu-id="cadd5-104">Migrar o Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="cadd5-104">Migrate Address Book</span></span>

<span data-ttu-id="cadd5-105">Em geral, o catálogo de endereços é migrado juntamente com o restante da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="cadd5-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="cadd5-106">No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente herdado:</span><span class="sxs-lookup"><span data-stu-id="cadd5-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="cadd5-107">Personalizadas as regras de normalização do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="cadd5-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="cadd5-108">Alterado o valor padrão para o parâmetro **UseNormalizationRules** para false.</span><span class="sxs-lookup"><span data-stu-id="cadd5-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="cadd5-109">**Regras de normalização de catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="cadd5-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="cadd5-110">Se você personalizou as regras de normalização de catálogo de endereços em seu ambiente herdado, deve migrar as regras personalizadas para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="cadd5-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="cadd5-111">Se você não tiver personalizado as regras de normalização de catálogo de endereços, não há nada para migrar para o serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="cadd5-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="cadd5-112">As regras de normalização padrão do Skype for Business Server 2019 são as mesmas regras padrão para a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="cadd5-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="cadd5-113">Siga o procedimento mais adiante nesta seção para migrar regras de normalização personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cadd5-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="cadd5-114">Se a sua organização usa o controle de chamada remota e você personalizou regras de normalização de catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="cadd5-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="cadd5-115">O procedimento requer associação no grupo RTCUniversalServerAdmins ou direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="cadd5-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="cadd5-116">**UseNormalizationRules definido como false**</span><span class="sxs-lookup"><span data-stu-id="cadd5-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="cadd5-117">Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone conforme são definidos nos serviços de domínio Active Directory sem ter o Skype for Business Server 2019, aplique as regras de normalização, você precisa definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** para true.</span><span class="sxs-lookup"><span data-stu-id="cadd5-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="cadd5-118">Siga o procedimento mais adiante nesta seção para definir esses parâmetros como true.</span><span class="sxs-lookup"><span data-stu-id="cadd5-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="cadd5-119">Para migrar regras de normalização personalizadas do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="cadd5-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="cadd5-120">Localize o arquivo Company_Phone_Number_Normalization_Rules. txt na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços no pool piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cadd5-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cadd5-121">O exemplo de regras de normalização de catálogo de endereços foi instalado no diretório de arquivos do componente da Web do ABS.</span><span class="sxs-lookup"><span data-stu-id="cadd5-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="cadd5-122">O caminho é **$installedDriveLetter: \Arquivos de Programas\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**.</span><span class="sxs-lookup"><span data-stu-id="cadd5-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="cadd5-123">Esse arquivo pode ser copiado e renomeado como **Company_Phone_Number_Normalization_Rules. txt** para o diretório raiz da pasta compartilhada do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="cadd5-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="cadd5-124">Por exemplo, o catálogo de endereços compartilhado no **$serverX**, o caminho será semelhante a: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="cadd5-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="cadd5-125">Use um editor de texto, como o bloco de notas, para abrir o arquivo Company_Phone_Number_Normalization_Rules. txt.</span><span class="sxs-lookup"><span data-stu-id="cadd5-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="cadd5-126">Certos tipos de entradas não funcionarão corretamente no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cadd5-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="cadd5-127">Examine o arquivo para ver os tipos de entradas descritos nesta etapa, edite-os conforme necessário e salve as alterações na pasta compartilhada do catálogo de endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="cadd5-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="cadd5-128">As cadeias de caracteres que incluem espaço em branco ou Pontuação necessários provocam falha nas regras de normalização porque esses caracteres são removidos da cadeia de caracteres que é inserida nas regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="cadd5-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="cadd5-129">Se você tiver cadeias de caracteres que incluam espaço em branco ou pontuação necessária, será necessário modificar as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cadd5-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="cadd5-130">Por exemplo, a cadeia de caracteres a seguir causa falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="cadd5-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="cadd5-131">A cadeia de caracteres a seguir não causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="cadd5-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="cadd5-132">Para definir UseNormalizationRules e IgnoreGenericRules como true</span><span class="sxs-lookup"><span data-stu-id="cadd5-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="cadd5-133">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="cadd5-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="cadd5-134">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cadd5-134">Do one of the following:</span></span>

   - <span data-ttu-id="cadd5-135">Se sua implantação incluir somente o Skype for Business Server 2019, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true:</span><span class="sxs-lookup"><span data-stu-id="cadd5-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="cadd5-136">Se a sua implantação inclui uma combinação do Skype for Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribua-o a cada pool do Skype for Business Server 2019 na topologia:</span><span class="sxs-lookup"><span data-stu-id="cadd5-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="cadd5-137">Aguarde até que a replicação do repositório de gerenciamento central ocorra em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="cadd5-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="cadd5-138">Modifique o arquivo de regras de normalização de telefone, "Company_Phone_Number_Normalization_Rules. txt", para sua implantação para limpar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cadd5-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="cadd5-139">O arquivo está no compartilhamento de arquivos de cada pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cadd5-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cadd5-140">Se o arquivo não estiver presente, crie um arquivo vazio chamado "Company_Phone_Number_Normalization_Rules. txt".</span><span class="sxs-lookup"><span data-stu-id="cadd5-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="cadd5-141">Aguarde alguns minutos para que todos os pools de front-end leiam os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="cadd5-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="cadd5-142">Execute o seguinte cmdlet em cada pool do Skype for Business Server 2019 na sua implantação:</span><span class="sxs-lookup"><span data-stu-id="cadd5-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


