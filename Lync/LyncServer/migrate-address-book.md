---
title: Migrar o Catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="df695-102">Migrar o Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="df695-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df695-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="df695-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="df695-104">Em geral, o catálogo de endereços do Lync Server 2010 é migrado juntamente com o restante da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="df695-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="df695-105">No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente do Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="df695-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="df695-106">Defina a propriedade WMI **PartitionbyOU** como entradas do catálogo de endereços de grupo por unidade organizacional (ou).</span><span class="sxs-lookup"><span data-stu-id="df695-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="df695-107">Personalizadas as regras de normalização do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="df695-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="df695-108">Alterado o valor padrão para o parâmetro **UseNormalizationRules** para false.</span><span class="sxs-lookup"><span data-stu-id="df695-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="df695-109">**Entradas do catálogo de endereços agrupadas**</span><span class="sxs-lookup"><span data-stu-id="df695-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="df695-110">Se você definir a propriedade WMI **PartitionbyOU** como true para criar catálogos de endereços para cada UO, será necessário definir o atributo **msRTCSIP-Groupingid** do Active Directory em usuários e contatos se quiser continuar a agrupar as entradas do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="df695-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="df695-111">Você pode querer agrupar entradas de catálogo de endereços para limitar o escopo das pesquisas do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="df695-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="df695-112">Para usar o atributo **msRTCSIP-groupingid** , escreva um script para preencher o atributo, atribuindo o mesmo valor para todos os usuários que você deseja agrupar juntos.</span><span class="sxs-lookup"><span data-stu-id="df695-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="df695-113">Por exemplo, atribua um único valor para todos os usuários de uma OU.</span><span class="sxs-lookup"><span data-stu-id="df695-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="df695-114">**Regras de normalização de catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="df695-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="df695-115">Se você personalizou as regras de normalização de catálogo de endereços no ambiente do Lync Server 2010, deve migrar as regras personalizadas para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="df695-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="df695-116">Se você não tiver personalizado as regras de normalização de catálogo de endereços, não há nada para migrar para o serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="df695-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="df695-117">As regras de normalização padrão do Lync Server 2013 são iguais às regras padrão do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df695-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="df695-118">Siga o procedimento mais adiante nesta seção para migrar regras de normalização personalizadas.</span><span class="sxs-lookup"><span data-stu-id="df695-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df695-119">Se a sua organização usa o controle de chamada remota e você personalizou regras de normalização de catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="df695-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="df695-120">O procedimento requer associação no grupo RTCUniversalServerAdmins ou direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="df695-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="df695-121">**UseNormalizationRules definido como false**</span><span class="sxs-lookup"><span data-stu-id="df695-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="df695-122">Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone conforme são definidos nos serviços de domínio Active Directory sem ter o Lync Server 2013 aplicar as regras de normalização, você precisa definir o \*\*UseNormalizationRules \*\*e os parâmetros **IgnoreGenericRules** para true.</span><span class="sxs-lookup"><span data-stu-id="df695-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="df695-123">Siga o procedimento mais adiante nesta seção para definir esses parâmetros como true.</span><span class="sxs-lookup"><span data-stu-id="df695-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="df695-124">Para migrar regras de normalização personalizadas do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="df695-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="df695-125">Localize o arquivo\_.\_txt\_das\_regras de normalização de número de telefone da empresa na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços no pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df695-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df695-126">O exemplo de regras de normalização de catálogo de endereços foi instalado no diretório de arquivos do componente da Web do ABS.</span><span class="sxs-lookup"><span data-stu-id="df695-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="df695-127">O caminho é <STRONG>$installedDriveLetter: \Arquivos de Programas\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="df695-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="df695-128">Esse arquivo pode ser copiado e renomeado &nbsp;como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para o diretório raiz da pasta compartilhada do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="df695-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="df695-129">Por exemplo, o catálogo de endereços compartilhado <STRONG></STRONG>no $serverX&nbsp;, o caminho será semelhante a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="df695-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="df695-130">Use um editor de texto, como o bloco de notas, para\_abrir\_o\_arquivo de\_regras de normalização de número de telefone da empresa. txt.</span><span class="sxs-lookup"><span data-stu-id="df695-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="df695-131">Certos tipos de entradas não funcionarão corretamente no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df695-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="df695-132">Examine o arquivo para ver os tipos de entradas descritos nesta etapa, edite-os conforme necessário e salve as alterações na pasta compartilhada do catálogo de endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="df695-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="df695-133">As cadeias de caracteres que incluem espaço em branco ou Pontuação necessários provocam falha nas regras de normalização porque esses caracteres são removidos da cadeia de caracteres que é inserida nas regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="df695-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="df695-134">Se você tiver cadeias de caracteres que incluam espaço em branco ou pontuação necessária, será necessário modificar as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="df695-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="df695-135">Por exemplo, a cadeia de caracteres a seguir causa falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="df695-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="df695-136">A cadeia de caracteres a seguir não causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="df695-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="df695-137">Para definir UseNormalizationRules e IgnoreGenericRules como true</span><span class="sxs-lookup"><span data-stu-id="df695-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="df695-138">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="df695-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df695-139">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="df695-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="df695-140">Se a sua implantação incluir somente o Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true:</span><span class="sxs-lookup"><span data-stu-id="df695-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="df695-141">Se a sua implantação inclui uma combinação de Lync Server 2013 e Lync Server 2010 ou o Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:</span><span class="sxs-lookup"><span data-stu-id="df695-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="df695-142">Aguarde até que a replicação do repositório de gerenciamento central ocorra em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="df695-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="df695-143">Modifique o arquivo de regras de normalização de telefone\_,\_"\_\_regras de normalização de número de telefone da empresa. txt", para que sua implantação Limpe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="df695-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="df695-144">O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df695-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="df695-145">Se o arquivo não estiver presente, crie um arquivo\_vazio chamado "\_\_\_regras de normalidade de número de telefone da empresa. txt".</span><span class="sxs-lookup"><span data-stu-id="df695-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="df695-146">Aguarde alguns minutos para que todos os pools de front-end leiam os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="df695-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="df695-147">Execute o seguinte cmdlet em cada pool do Lync Server 2013 em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="df695-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

