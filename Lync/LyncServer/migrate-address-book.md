---
title: Migrar catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8581e36019cad7a3ac3aef80369e2daec6179f72
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="65bb3-102">Migrar o Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="65bb3-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65bb3-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="65bb3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="65bb3-104">Em geral, o catálogo de endereços do Lync Server 2010 é migrado junto com o restante da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="65bb3-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="65bb3-105">No entanto, talvez seja necessário executar algumas etapas de migração após a personalização do seguinte no seu ambiente do Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="65bb3-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="65bb3-106">Defina a propriedade de WMI **PartitionbyOU** para agrupar entradas do Catálogo de Endereços por unidade organizacional (UO).</span><span class="sxs-lookup"><span data-stu-id="65bb3-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="65bb3-107">Personalizou as regras de normalização do Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="65bb3-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="65bb3-108">Alterou o valor padrão do parâmetro **UseNormalizationRules** para Falso.</span><span class="sxs-lookup"><span data-stu-id="65bb3-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="65bb3-109">**Agrupou entradas do Catálogo de Endereços**</span><span class="sxs-lookup"><span data-stu-id="65bb3-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="65bb3-p102">Se você definiu a propriedade de WMI **PartitionbyOU** como True para criar catálogos de endereços para cada UO, é necessário definir o atributo **msRTCSIP-GroupingId** do Active Directory sobre usuários e contatos se você deseja continuar agrupando entradas do catálogo de endereços. Pode ser desejável agrupar entradas do catálogo de endereços para limitar o escopo das pesquisas no Catálogo. Para usar o atributo **msRTCSIP-GroupingId**, escreva um script para popular o atributo, atribuindo o mesmo valor para todos os usuários que você deseja agrupar. Por exemplo, atribua um valor único para todos os usuários em uma UO.</span><span class="sxs-lookup"><span data-stu-id="65bb3-p102">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="65bb3-114">**Regras de Normalização do Catálogo de Endereços**</span><span class="sxs-lookup"><span data-stu-id="65bb3-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="65bb3-115">Se você personalizou as regras de normalização do catálogo de endereços no seu ambiente do Lync Server 2010, você deve migrar as regras personalizadas para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="65bb3-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="65bb3-116">Se você não personalizou regras de normalização do Catálogo de Endereços, não há nada para migrar para o serviço do Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="65bb3-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="65bb3-117">As regras de normalização padrão para o Lync Server 2013 são as mesmas regras padrão para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="65bb3-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="65bb3-118">Siga o procedimento posteriormente nesta seção para migrar regras de normalização personalizadas.</span><span class="sxs-lookup"><span data-stu-id="65bb3-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65bb3-p104">Se sua organização usa controle de chamadas remotas e você personalizou regras de normalização do Catálogo de Endereços, deve executar o procedimento deste tópico antes de usar o controle de chamadas remotas. O procedimento requer a associação no grupo RTCUniversalServerAdmins ou direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="65bb3-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="65bb3-121">**UseNormalizationRules definido como Falso**</span><span class="sxs-lookup"><span data-stu-id="65bb3-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="65bb3-122">Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone como definidos nos serviços de domínio do Active Directory sem ter o Lync Server 2013 aplicar regras de normalização, você precisará definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** como true.</span><span class="sxs-lookup"><span data-stu-id="65bb3-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="65bb3-123">Siga o procedimento posteriormente nesta seção para definir esses parâmetros como Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="65bb3-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="65bb3-124">Para migrar regras de normalização personalizadas do Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="65bb3-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="65bb3-125">Encontre o arquivo\_de\_\_regras\_de normalização de número de telefone da empresa na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços em seu pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65bb3-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65bb3-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span><span class="sxs-lookup"><span data-stu-id="65bb3-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="65bb3-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="65bb3-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="65bb3-128">Esse arquivo pode ser copiado e renomeado &nbsp;como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para o diretório raiz da pasta compartilhada do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="65bb3-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="65bb3-129">Por exemplo, o catálogo de endereços compartilhado <STRONG></STRONG>no $serverX&nbsp;, o caminho será semelhante a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="65bb3-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="65bb3-130">Use um editor de texto, como o bloco de notas, para\_abrir\_o\_arquivo de\_regras de normalização de número de telefone da empresa. txt.</span><span class="sxs-lookup"><span data-stu-id="65bb3-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="65bb3-131">Determinados tipos de entradas não funcionarão corretamente no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65bb3-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="65bb3-132">Pesquise no arquivo pelos tipos de entrada descritos nesta etapa,m edite-os conforme o necessário e salve as alterações na pasta compartilhada do Catálogo de Endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="65bb3-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="65bb3-p108">Cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios causam falha nas regras de normalização porque estes caracteres são excluídos da cadeia de caracteres que serve como entrada para as regras de normalização. Se você tem cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios, é necessário modificá-las. Por exemplo, a cadeia de caracteres a seguir causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="65bb3-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="65bb3-136">A cadeia de caracteres a seguir não causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="65bb3-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="65bb3-137">Para definir UseNormalizationRules e IgnoreGenericRules como verdadeiro</span><span class="sxs-lookup"><span data-stu-id="65bb3-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="65bb3-138">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="65bb3-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="65bb3-139">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="65bb3-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="65bb3-140">Se sua implantação incluir somente o Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true:</span><span class="sxs-lookup"><span data-stu-id="65bb3-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="65bb3-141">Se sua implantação incluir uma combinação do Lync Server 2013 e do Lync Server 2010 ou do Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:</span><span class="sxs-lookup"><span data-stu-id="65bb3-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="65bb3-142">Aguarde a replicação do repositório de gerenciamento central ocorrer em todos os pools.</span><span class="sxs-lookup"><span data-stu-id="65bb3-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="65bb3-143">Modifique o arquivo de regras de normalização de telefone\_,\_"\_\_regras de normalização de número de telefone da empresa", para que sua implantação Limpe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="65bb3-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="65bb3-144">O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65bb3-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="65bb3-145">Se o arquivo não estiver presente, crie um arquivo\_vazio chamado "\_\_\_regras de normalização de número de telefone da empresa. txt".</span><span class="sxs-lookup"><span data-stu-id="65bb3-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="65bb3-146">Aguarde alguns minutos para que todos os pools de front-ends leiam os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="65bb3-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="65bb3-147">Execute o cmdlet a seguir em cada pool do Lync Server 2013 em sua implantação:</span><span class="sxs-lookup"><span data-stu-id="65bb3-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

