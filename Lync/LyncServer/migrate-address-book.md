---
title: Migrar catálogo de endereços
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar o Catálogo de Endereços

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Em geral, o catálogo de endereços do Lync Server 2010 é migrado junto com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração após a personalização do seguinte no seu ambiente do Lync Server 2010:

  - Defina a propriedade de WMI **PartitionbyOU** para agrupar entradas do Catálogo de Endereços por unidade organizacional (UO).

  - Personalizou as regras de normalização do Catálogo de Endereços

  - Alterou o valor padrão do parâmetro **UseNormalizationRules** para Falso.

**Agrupou entradas do Catálogo de Endereços**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**Regras de Normalização do Catálogo de Endereços**

Se você personalizou as regras de normalização do catálogo de endereços no seu ambiente do Lync Server 2010, você deve migrar as regras personalizadas para o pool piloto. Se você não personalizou regras de normalização do Catálogo de Endereços, não há nada para migrar para o serviço do Catálogo de Endereços. As regras de normalização padrão para o Lync Server 2013 são as mesmas regras padrão para o Lync Server 2010. Siga o procedimento posteriormente nesta seção para migrar regras de normalização personalizadas.

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**UseNormalizationRules definido como Falso**

Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone como definidos nos serviços de domínio do Active Directory sem ter o Lync Server 2013 aplicar regras de normalização, você precisará definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** como true. Siga o procedimento posteriormente nesta seção para definir esses parâmetros como Verdadeiro.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar regras de normalização personalizadas do Catálogo de Endereços

1.  Encontre o \_ arquivo de \_Rules.txt normalização de número de telefone da empresa \_ \_ na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços em seu pool piloto do Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > The sample Address Book normalization rules have been installed in your ABS Web component file directory. The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Esse arquivo pode ser copiado e renomeado como &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; para o diretório raiz da pasta compartilhada do catálogo de endereços. Por exemplo, o catálogo de endereços compartilhado no <STRONG>$serverX</STRONG>, &nbsp; o caminho será semelhante a: <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Use um editor de texto, como o bloco de notas, para abrir o \_ arquivo normalização de número de telefone da empresa \_ \_ \_Rules.txt.

3.  Determinados tipos de entradas não funcionarão corretamente no Lync Server 2013. Pesquise no arquivo pelos tipos de entrada descritos nesta etapa,m edite-os conforme o necessário e salve as alterações na pasta compartilhada do Catálogo de Endereços em seu pool piloto.
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    A cadeia de caracteres a seguir não causaria falha na regra de normalização:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para definir UseNormalizationRules e IgnoreGenericRules como verdadeiro

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Siga um destes procedimentos:
    
      - Se sua implantação incluir somente o Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se sua implantação incluir uma combinação do Lync Server 2013 e do Lync Server 2010 ou do Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Aguarde a replicação do repositório de gerenciamento central ocorrer em todos os pools.

4.  Modifique o arquivo de regras de normalização de telefone, " \_ \_ normalização de número de telefone da empresa \_ \_Rules.txt", para que sua implantação Limpe o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013. Se o arquivo não estiver presente, crie um arquivo vazio chamado " \_ normalização de número de telefone da empresa \_ \_ \_Rules.txt".

5.  Aguarde alguns minutos para que todos os pools de front-ends leiam os novos arquivos.

6.  Execute o cmdlet a seguir em cada pool do Lync Server 2013 em sua implantação:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

