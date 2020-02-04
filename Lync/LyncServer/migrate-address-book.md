---
title: Migrar o Catálogo de endereços
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
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrar o Catálogo de endereços

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Em geral, o catálogo de endereços do Lync Server 2010 é migrado juntamente com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente do Lync Server 2010:

  - Defina a propriedade WMI **PartitionbyOU** como entradas do catálogo de endereços de grupo por unidade organizacional (ou).

  - Personalizadas as regras de normalização do catálogo de endereços.

  - Alterado o valor padrão para o parâmetro **UseNormalizationRules** para false.

**Entradas do catálogo de endereços agrupadas**

Se você definir a propriedade WMI **PartitionbyOU** como true para criar catálogos de endereços para cada UO, será necessário definir o atributo **msRTCSIP-Groupingid** do Active Directory em usuários e contatos se quiser continuar a agrupar as entradas do catálogo de endereços. Você pode querer agrupar entradas de catálogo de endereços para limitar o escopo das pesquisas do catálogo de endereços. Para usar o atributo **msRTCSIP-groupingid** , escreva um script para preencher o atributo, atribuindo o mesmo valor para todos os usuários que você deseja agrupar juntos. Por exemplo, atribua um único valor para todos os usuários de uma OU.

**Regras de normalização de catálogo de endereços**

Se você personalizou as regras de normalização de catálogo de endereços no ambiente do Lync Server 2010, deve migrar as regras personalizadas para o pool piloto. Se você não tiver personalizado as regras de normalização de catálogo de endereços, não há nada para migrar para o serviço de catálogo de endereços. As regras de normalização padrão do Lync Server 2013 são iguais às regras padrão do Lync Server 2010. Siga o procedimento mais adiante nesta seção para migrar regras de normalização personalizadas.

<div>


> [!NOTE]  
> Se a sua organização usa o controle de chamada remota e você personalizou regras de normalização de catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota. O procedimento requer associação no grupo RTCUniversalServerAdmins ou direitos equivalentes.



</div>

**UseNormalizationRules definido como false**

Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone como são definidos nos serviços de domínio Active Directory sem ter o Lync Server 2013 aplicar as regras de normalização, você precisará definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** para true. Siga o procedimento mais adiante nesta seção para definir esses parâmetros como true.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar regras de normalização personalizadas do catálogo de endereços

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para definir UseNormalizationRules e IgnoreGenericRules como true

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Siga um destes procedimentos:
    
      - Se a sua implantação incluir somente o Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se a sua implantação inclui uma combinação de Lync Server 2013 e Lync Server 2010 ou o Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Aguarde até que a replicação do repositório de gerenciamento central ocorra em todos os pools.

4.  Modifique o arquivo de regras de normalização de telefone\_,\_"\_\_regras de normalização de número de telefone da empresa. txt", para que sua implantação Limpe o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013. Se o arquivo não estiver presente, crie um arquivo\_vazio chamado "\_\_\_regras de normalidade de número de telefone da empresa. txt".

5.  Aguarde alguns minutos para que todos os pools de front-end leiam os novos arquivos.

6.  Execute o seguinte cmdlet em cada pool do Lync Server 2013 em sua implantação:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

