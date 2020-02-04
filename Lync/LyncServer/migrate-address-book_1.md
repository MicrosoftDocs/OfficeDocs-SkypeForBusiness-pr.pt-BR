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

# <a name="migrate-address-book"></a>Migrar o Catálogo de endereços

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

**Para migrar regras de normalização personalizadas do catálogo de endereços**

1.  Localize o arquivo\_.\_txt\_das\_regras de normalização de número de telefone da empresa na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços no pool piloto do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > O exemplo de regras de normalização de catálogo de endereços foi instalado no diretório de arquivos do componente da Web do ABS. O caminho é <STRONG>$installedDriveLetter: \Arquivos de Programas\microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>. Esse arquivo pode ser copiado e renomeado &nbsp;como <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;para o diretório raiz da pasta compartilhada do catálogo de endereços. Por exemplo, o catálogo de endereços compartilhado <STRONG></STRONG>no $serverX&nbsp;, o caminho será semelhante a: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Use um editor de texto, como o bloco de notas, para\_abrir\_o\_arquivo de\_regras de normalização de número de telefone da empresa. txt.

3.  Certos tipos de entradas não funcionarão corretamente no Lync Server 2013. Examine o arquivo para ver os tipos de entradas descritos nesta etapa, edite-os conforme necessário e salve as alterações na pasta compartilhada do catálogo de endereços em seu pool piloto.
    
    As cadeias de caracteres que incluem espaço em branco ou Pontuação necessários provocam falha nas regras de normalização porque esses caracteres são removidos da cadeia de caracteres que é inserida nas regras de normalização. Se você tiver cadeias de caracteres que incluam espaço em branco ou pontuação necessária, será necessário modificar as cadeias de caracteres. Por exemplo, a cadeia de caracteres a seguir causa falha na regra de normalização:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    A cadeia de caracteres a seguir não causaria falha na regra de normalização:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

