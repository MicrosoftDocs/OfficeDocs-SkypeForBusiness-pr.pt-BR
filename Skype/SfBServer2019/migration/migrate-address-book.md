---
title: Migrar catálogo de endereços
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Em geral, o Address Book é migrado junto com o restante da sua topologia. No entanto, talvez você precise executar algumas etapas pós-migração se tiver personalizado o seguinte em seu ambiente herdado:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752833"
---
# <a name="migrate-address-book"></a><span data-ttu-id="f45bf-104">Migrar o Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="f45bf-104">Migrate Address Book</span></span>

<span data-ttu-id="f45bf-105">Em geral, o Address Book é migrado junto com o restante da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f45bf-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f45bf-106">No entanto, talvez você precise executar algumas etapas pós-migração se tiver personalizado o seguinte em seu ambiente herdado:</span><span class="sxs-lookup"><span data-stu-id="f45bf-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="f45bf-107">Personalizou as regras de normalização do Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="f45bf-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="f45bf-108">Alterou o valor padrão do parâmetro **UseNormalizationRules** para Falso.</span><span class="sxs-lookup"><span data-stu-id="f45bf-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="f45bf-109">**Regras de Normalização do Catálogo de Endereços**</span><span class="sxs-lookup"><span data-stu-id="f45bf-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f45bf-110">Se você personalizava regras de normalização do Livro de Endereços em seu ambiente herdado, você deve migrar as regras personalizadas para seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="f45bf-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f45bf-111">Se você não personalizou regras de normalização do Catálogo de Endereços, não há nada para migrar para o serviço do Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="f45bf-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f45bf-112">As regras de normalização padrão do Skype for Business Server 2019 são as mesmas regras padrão para a instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="f45bf-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="f45bf-113">Siga o procedimento posteriormente nesta seção para migrar regras de normalização personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f45bf-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="f45bf-p104">Se sua organização usa controle de chamadas remotas e você personalizou regras de normalização do Catálogo de Endereços, deve executar o procedimento deste tópico antes de usar o controle de chamadas remotas. O procedimento requer a associação no grupo RTCUniversalServerAdmins ou direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f45bf-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="f45bf-116">**UseNormalizationRules definido como Falso**</span><span class="sxs-lookup"><span data-stu-id="f45bf-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f45bf-117">Se você definir o valor de **UseNormalizationRules** como False para que os usuários possam usar números de telefone conforme definidos nos Serviços de Domínio Active Directory sem que o Skype for Business Server 2019 aplique regras de normalização, será necessário definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** como True.</span><span class="sxs-lookup"><span data-stu-id="f45bf-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f45bf-118">Siga o procedimento posteriormente nesta seção para definir esses parâmetros como Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="f45bf-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f45bf-119">Para migrar regras de normalização personalizadas do Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="f45bf-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="f45bf-120">Encontre o Company_Phone_Number_Normalization_Rules.txt na raiz da pasta compartilhada do Livro de Endereços e copie-o para a raiz da pasta compartilhada do Livro de Endereços no pool piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f45bf-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f45bf-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span><span class="sxs-lookup"><span data-stu-id="f45bf-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f45bf-122">O caminho é **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="f45bf-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="f45bf-123">Esse arquivo pode ser copiado e renomeado como **Company_Phone_Number_Normalization_Rules.txt** para o diretório raiz da pasta compartilhada do livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="f45bf-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="f45bf-124">Por exemplo, o livro de endereços compartilhado no **$serverX**, o caminho será semelhante **\\ a: $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span><span class="sxs-lookup"><span data-stu-id="f45bf-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="f45bf-125">Use um editor de texto, como o Bloco de Notas para abrir o arquivo Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="f45bf-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="f45bf-126">Determinados tipos de entradas não funcionarão corretamente no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f45bf-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="f45bf-127">Pesquise no arquivo pelos tipos de entrada descritos nesta etapa,m edite-os conforme o necessário e salve as alterações na pasta compartilhada do Catálogo de Endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="f45bf-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="f45bf-p108">Cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios causam falha nas regras de normalização porque estes caracteres são excluídos da cadeia de caracteres que serve como entrada para as regras de normalização. Se você tem cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios, é necessário modificá-las. Por exemplo, a cadeia de caracteres a seguir causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="f45bf-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="f45bf-131">A cadeia de caracteres a seguir não causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="f45bf-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f45bf-132">Para definir UseNormalizationRules e IgnoreGenericRules como verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f45bf-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="f45bf-133">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="f45bf-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f45bf-134">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f45bf-134">Do one of the following:</span></span>

   - <span data-ttu-id="f45bf-135">Se sua implantação incluir apenas o Skype for Business Server 2019, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para True:</span><span class="sxs-lookup"><span data-stu-id="f45bf-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="f45bf-136">Se sua implantação inclui uma combinação do Skype for Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribua-o a cada pool do Skype for Business Server 2019 na topologia:</span><span class="sxs-lookup"><span data-stu-id="f45bf-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="f45bf-137">Aguarde a replicação do armazenamento de Gerenciamento Central ocorrer em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="f45bf-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="f45bf-138">Modifique o arquivo de regras de normalização de telefone, "Company_Phone_Number_Normalization_Rules.txt", para sua implantação apagar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f45bf-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f45bf-139">O arquivo está no compartilhamento de arquivos de cada pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f45bf-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f45bf-140">Se o arquivo não estiver presente, crie então um arquivo vazio chamado "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="f45bf-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="f45bf-141">Aguarde vários minutos para que todos os pools de Front End leiam os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="f45bf-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="f45bf-142">Execute o seguinte cmdlet em cada pool do Skype for Business Server 2019 em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="f45bf-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


