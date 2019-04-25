---
title: Migrar o Catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Em geral, o catálogo de endereços é migrado com o restante de sua topologia. No entanto, você talvez precise executar algumas etapas de pós-migração se você personalizou o seguinte no seu ambiente Herdado:'
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238421"
---
# <a name="migrate-address-book"></a><span data-ttu-id="b76f4-104">Migrar o Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="b76f4-104">Migrate Address Book</span></span>

<span data-ttu-id="b76f4-105">Em geral, o catálogo de endereços é migrado com o restante de sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b76f4-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="b76f4-106">No entanto, você talvez precise executar algumas etapas de pós-migração se você personalizou o seguinte no seu ambiente Herdado:</span><span class="sxs-lookup"><span data-stu-id="b76f4-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="b76f4-107">Personalizou as regras de normalização do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="b76f4-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="b76f4-108">Alterado o valor padrão do parâmetro **UseNormalizationRules** para falso.</span><span class="sxs-lookup"><span data-stu-id="b76f4-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="b76f4-109">**Regras de normalização do catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="b76f4-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="b76f4-110">Se você personalizou regras de normalização do catálogo de endereços em seu ambiente herdado, você deve migrar as regras personalizadas para seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="b76f4-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="b76f4-111">Se você não personalizar regras de normalização do catálogo de endereços, você não tem nada para migrar para o serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="b76f4-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="b76f4-112">As regras de normalização padrão para Skype para Business Server 2019 são os mesmos as regras padrão para a instalação de legado.</span><span class="sxs-lookup"><span data-stu-id="b76f4-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="b76f4-113">Siga o procedimento nesta seção para migrar regras de normalização personalizada.</span><span class="sxs-lookup"><span data-stu-id="b76f4-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="b76f4-114">Se sua organização usa controle de chamada remota e você personalizou regras de normalização do catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="b76f4-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="b76f4-115">O procedimento requer a participação no grupo RTCUniversalServerAdmins ou direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="b76f4-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="b76f4-116">**UseNormalizationRules definido como falso**</span><span class="sxs-lookup"><span data-stu-id="b76f4-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="b76f4-117">Se definir o valor de **UseNormalizationRules** como False para que os usuários possam usar números de telefone como eles são definidos no Active Directory Domain Services sem ter que Skype para Business Server 2019 aplicar regras de normalização, você precisará definir o \*\* UseNormalizationRules\*\* e os parâmetros de **IgnoreGenericRules** como True.</span><span class="sxs-lookup"><span data-stu-id="b76f4-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="b76f4-118">Siga o procedimento nesta seção para definir esses parâmetros como True.</span><span class="sxs-lookup"><span data-stu-id="b76f4-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="b76f4-119">Para migrar o catálogo de endereços personalizou regras de normalização</span><span class="sxs-lookup"><span data-stu-id="b76f4-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="b76f4-120">Encontre o arquivo company_phone_number_normalization_rules txt na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços em seu Skype para o pool piloto Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b76f4-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b76f4-121">As regras de normalização do catálogo de endereços de amostra tenham sido instaladas no seu diretório de arquivo do componente Web ABS.</span><span class="sxs-lookup"><span data-stu-id="b76f4-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="b76f4-122">O caminho é **$installedDriveLetter: \Program Files\Microsoft Skype para Business Server 2019\Web Components\Address catálogo Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="b76f4-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="b76f4-123">Esse arquivo possa ser copiado e renomeado como **company_phone_number_normalization_rules** para o diretório raiz do endereço catálogo compartilhado da pasta.</span><span class="sxs-lookup"><span data-stu-id="b76f4-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="b76f4-124">Por exemplo, o catálogo de endereços compartilhado em **$serverX**, o caminho será semelhante a: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="b76f4-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="b76f4-125">Use um editor de texto, como o bloco de notas, para abrir o arquivo company_phone_number_normalization_rules txt.</span><span class="sxs-lookup"><span data-stu-id="b76f4-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="b76f4-126">Certos tipos de entradas não funcionará corretamente no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b76f4-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="b76f4-127">Examine o arquivo para os tipos de entradas descritos nesta etapa, editá-los conforme o necessário e salvar as alterações para a pasta compartilhada do catálogo de endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="b76f4-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="b76f4-128">Cadeias de caracteres que incluem necessárias de espaço em branco ou pontuação causa regras de normalização falhe, pois esses caracteres são removidos sem a cadeia de caracteres que é de entrada para as regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="b76f4-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="b76f4-129">Se você tiver as cadeias de caracteres que incluem necessário de espaço em branco ou pontuação, você precisará modificar as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b76f4-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="b76f4-130">Por exemplo, a seguinte sequência causaria Falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="b76f4-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="b76f4-131">A cadeia de caracteres a seguir não causaria Falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="b76f4-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="b76f4-132">Para definir UseNormalizationRules e IgnoreGenericRules como true</span><span class="sxs-lookup"><span data-stu-id="b76f4-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="b76f4-133">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="b76f4-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b76f4-134">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b76f4-134">Do one of the following:</span></span>

   - <span data-ttu-id="b76f4-135">Se sua implantação incluir apenas Skype para Business Server 2019, execute o seguinte cmdlet em nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="b76f4-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="b76f4-136">Se sua implantação incluir uma combinação de Skype para Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribuí-lo a cada Skype para Business Server 2019 pool na topologia:</span><span class="sxs-lookup"><span data-stu-id="b76f4-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="b76f4-137">Aguarde a replicação do repositório de gerenciamento Central ocorra em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="b76f4-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="b76f4-138">Modifica o arquivo de regras de normalização de telefone, "Company_phone_number_normalization_rules", para sua implantação limpar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b76f4-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="b76f4-139">O arquivo está no compartilhamento de arquivos de cada Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="b76f4-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b76f4-140">Se o arquivo não estiver presente, em seguida, crie um arquivo vazio chamado "Company_phone_number_normalization_rules".</span><span class="sxs-lookup"><span data-stu-id="b76f4-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="b76f4-141">Espere alguns minutos para todos os pools de Front-End ler os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="b76f4-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="b76f4-142">Execute o seguinte cmdlet em cada Skype para Business Server 2019 pool em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="b76f4-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


