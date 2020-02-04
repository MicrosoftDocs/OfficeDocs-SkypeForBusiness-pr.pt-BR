---
title: Migrar o Catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="49b16-102">Migrar o Catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="49b16-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49b16-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="49b16-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="49b16-104">**Para migrar regras de normalização personalizadas do catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="49b16-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="49b16-105">Localize o arquivo\_.\_txt\_das\_regras de normalização de número de telefone da empresa na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços no pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49b16-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49b16-106">O exemplo de regras de normalização de catálogo de endereços foi instalado no diretório de arquivos do componente da Web do ABS.</span><span class="sxs-lookup"><span data-stu-id="49b16-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="49b16-107">O caminho é <STRONG>$installedDriveLetter: \Arquivos de Programas\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="49b16-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="49b16-108">Esse arquivo pode ser copiado e renomeado &nbsp;como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para o diretório raiz da pasta compartilhada do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="49b16-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="49b16-109">Por exemplo, o catálogo de endereços compartilhado <STRONG></STRONG>no $serverX&nbsp;, o caminho será semelhante a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="49b16-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="49b16-110">Use um editor de texto, como o bloco de notas, para\_abrir\_o\_arquivo de\_regras de normalização de número de telefone da empresa. txt.</span><span class="sxs-lookup"><span data-stu-id="49b16-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="49b16-111">Certos tipos de entradas não funcionarão corretamente no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49b16-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="49b16-112">Examine o arquivo para ver os tipos de entradas descritos nesta etapa, edite-os conforme necessário e salve as alterações na pasta compartilhada do catálogo de endereços em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="49b16-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="49b16-113">As cadeias de caracteres que incluem espaço em branco ou Pontuação necessários provocam falha nas regras de normalização porque esses caracteres são removidos da cadeia de caracteres que é inserida nas regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="49b16-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="49b16-114">Se você tiver cadeias de caracteres que incluam espaço em branco ou pontuação necessária, será necessário modificar as cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="49b16-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="49b16-115">Por exemplo, a cadeia de caracteres a seguir causa falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="49b16-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="49b16-116">A cadeia de caracteres a seguir não causaria falha na regra de normalização:</span><span class="sxs-lookup"><span data-stu-id="49b16-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

