---
title: 'Lync Server 2013: administrar o serviço de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Administrar o serviço de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

Como parte da implantação do Lync Server, Enterprise Edition ou do servidor Standard Edition, o serviço de catálogo de endereços é instalado por padrão. O banco de dados usado pelo serviço de catálogo de endereços – RTCab – é criado no SQL Server (para Enterprise Edition, esse é o servidor back-end do SQL Server; para o servidor Standard Edition, o SQL Server posicionado).

<div>


> [!NOTE]  
> Para obter informações sobre como usar o <STRONG>ADSI Edit</STRONG> para editar atributos de objeto dos serviços de domínio do Active Directory, consulte <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Para obter informações sobre uma ferramenta no kit de recursos especificamente para o serviço de catálogo de endereços, consulte <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalização de Número de Telefone do Servidor de Catálogo de Endereços

O Lync Server requer números de telefone padrão RFC 3966/E. 164. Para usar números de telefone não estruturados ou formatados inconsistentes, o Lync Server depende do servidor de catálogo de endereços para preprocessar números de telefone antes que eles sejam enviados para as regras de normalização. Quando um número de telefone é usado no catálogo de endereços e a regra de normalização é aplicada, os clientes, como o Lync Phone Edition e o Lync Mobile, podem usar esses números normalizados.

As regras de normalização que foram usadas nas versões anteriores podem não funcionar corretamente sem alguns ajustes. Como o espaço em branco e os caracteres não obrigatórios são removidos antes das regras de normalização, se sua expressão regex estiver procurando especificamente por um traço ou outro caractere que foi removido, a regra de normalização pode falhar. Você deve examinar as regras de normalização para verificar se elas não estão procurando por esses caracteres não obrigatórios, ou se a regra pode falhar normalmente e continuar com o evento onde a regra prevê que o caractere estaria presente mas não está.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Replicador de Usuários e Servidor de Catálogo de Endereços

O servidor de catálogo de endereços usa os dados fornecidos pelo Replicator de usuários para atualizar as informações que ele obtém inicialmente da lista de endereços global (GAL). O replicador de usuários grava os atributos de serviços de domínio do Active Directory para cada usuário, contato e grupo na tabela AbUserEntry no banco de dados e o servidor do catálogo de endereços sincroniza os dados do usuário do banco de dados em arquivos no repositório de arquivos do servidor do catálogo de endereços e no banco de dados do catálogo de endereços RTCab. O esquema da tabela de AbUserEntry usa duas colunas,   **UserGuid** e **UserData**. **Userguid** é a coluna de índice e contém o GUID de 16 bytes do objeto do Active Directory. **UserData** é uma coluna de imagem que contém todos os atributos de serviços de domínio do Active Directory mencionados anteriormente para esse contato.

O replicador de usuários determina quais atributos do Active Directory serão gravados lendo uma tabela de configuração localizada na mesma instância baseada no SQL Server que a tabela AbUserEntry. A tabela AbAttribute tem três colunas, **ID**, **Nome**, **Sinalizadores** e **Habilitar**. A tabela é criada durante a instalação do banco de dados. Se a tabela AbAttribute está vazia, o Replicador de usuários ignora a lógica de processamento da tabela AbUserEntry. Os atributos do servidor de catálogo de endereços são dinâmicos e recuperados da tabela AbAttribute, que inicialmente é gravada pelo servidor de catálogo de endereços quando o servidor de catálogo de endereços é ativado.

A ativação do servidor de catálogo de endereços preenche a tabela AbAttribute com os valores mostrados na tabela a seguir.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Nome</th>
<th>Sinalizadores</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>duas</p></td>
<td><p>SN</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3D</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>quatro</p></td>
<td><p>Título</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>0,5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Empresa</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11 </p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>Correio</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>Departamento</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>Descrição</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Gerente</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>508</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Os números na coluna **ID** devem ser exclusivos e nunca devem ser reutilizados. Além disso, manter os valores de ID em 256 poupa espaço nos arquivos de saída gravados pelo servidor do catálogo de endereços. No entanto, o valor de ID máximo é 65535. A coluna **nome** corresponde ao nome do atributo do Active Directory que o replicador de usuário deve colocar na tabela AbUserEntry para cada contato. O valor na coluna **sinalizadores** é usado para definir o tipo de atributo. Os seguintes tipos de atributos de servidor do catálogo de endereços são reconhecidos pelo replicador de usuários, indicado pelo byte inferior do valor na coluna **sinalizadores** .


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>Um atributo de seqüência de caracteres. O Replicador de usuário converte esse tipo em UTF-8 antes de armazená-lo na tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Um atributo binário. O Replicador de usuário armazena esse blob sem qualquer conversão.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Um atributo de cadeia de caracteres, mas é incluído apenas se o valor &quot;do atributo&quot;começa com Tel:. Isso é principalmente para atributos com valores múltiplos, especificamente <strong>proxyAddresses</strong>. Nesse caso, o servidor de catálogo de endereços está interessado <strong></strong> apenas em entradas de proxyAddresses &quot;que começam&quot;com Tel:. Portanto, com o intuito de economizar espaço, o replicador de usuários armazena apenas as entradas que &quot;começam com&quot;Tel:.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Um atributo de sequência de caracteres booliano, que se for VERDADEIRO faz com que o Replicador de usuário não inclua esse contato na tabela AbUserEntry. Se for FALSO, faz com que o Replicador de usuário inclua os atributos desse contato na tabela AbUserEntry, mas não o atributo específico com esse sinalizador. Este é outro tipo de caso especial que é principalmente para o atributo de <strong>msExchHideFromAddressLists</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Um atributo de cadeia de caracteres, mas é incluído apenas se o valor &quot;do atributo&quot; começa com SMTP &quot; @ &quot; : e inclui o símbolo.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Um atributo de cadeia de caracteres, mas é incluído apenas se o valor do &quot;atributo começa&quot; com &quot;Tel:&quot; ou SMTP: &quot; @ &quot; e inclui o símbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Se definido, é um atributo de valores múltiplos que pode aparecer mais de uma vez para cada contato.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Se definido, identifica o atributo de nome de conta de usuário do email de um contato. O servidor de catálogo de endereços usa esse sinalizador para identificar que valor de atributo mostrar na entrada do log de eventos de normalização do telefone.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se definido, identifica um atributo necessário para um contato. O servidor de catálogo de endereços inclui um usuário na tabela AbUserEntry somente se houver um valor para este atributo em Active Directory. Se houver mais de um atributo obrigatório, somente é necessário que um deles tenha que incluir o usuário em um valor na tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços sempre normaliza o valor desse atributo.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços usa o número normalizado de <strong>proxyAddresses</strong>, se a configuração de CMS do <strong>UseNormalizationRules</strong> é FALSO; caso contrário, ele se comporta igual a quando o bit de sinalizador é 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços não inclui os objetos que têm esse valor para o atributo especificado na tabela AbUserEntry. Por exemplo, se o atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tem esse bit de sinalizador definido, os contatos que tenham esse atributo não são gravados no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços não inclui objetos na tabela AbUserEntry que não possuam esse valor para o atributo especificado. Se os bits de sinalizador 0x4000 e 0x8000 são definidos em um objeto, o atributo com o valor de bit de sinalizador definido como 0x4000 terá precedência e o objeto é excluído da tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Se definido, representa um objeto de grupo. O Replicador de usuário usa esse bit de sinalizador para incluir os contatos com o  atributo de <strong>groupType</strong> cuja presença indica um grupo (por exemplo, uma lista de distribuição ou um grupo de segurança).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Se definido, o Replicador de usuário usa esse bit de sinalizador para incluir este atributo em arquivos de servidor de catálogo de endereços específicos de dispositivo (ou seja, arquivos com uma extensão .dabs).</p></td>
</tr>
</tbody>
</table>


Nas versões anteriores do Lync Server, ao aplicar uma alteração no Active Directory, o administrador seria necessário para executar **Update-CSUserDatabase** e **Update – CSAddressBook** Windows PowerShell cmdlets para persistir a alteração para o banco de dados de usuário do Lync Server e para o banco de dados do RTCab imediatamente. No Lync Server 2013, o replicador de usuários do Lync Server selecionará as alterações do Active Directory e atualizará o banco de dados de usuário do Lync Server com base em um intervalo configurado. O replicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook. Se a consulta web ao Catálogo de Endereços estiver habilitada, as mudanças serão refletidas nos resultados de busca por clientes Lync. Os administradores precisarão executar o Atualizar -CSAddressBook somente se o download de arquivo do Catálogo de Endereços estiver habilitado.

<div>


> [!NOTE]  
> Por padrão, o replicador de usuários do Lync Server é executado automaticamente a cada 5 minutos. Você pode configurar esse intervalo usando o set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrando o catálogo de endereços

Os usuários preenchidos nos arquivos do servidor do catálogo de endereços podem ser controlados com base em determinados atributos dos serviços de domínio do Active Directory listados na tabela AbAttribute. Um desses atributos que é usado para a filtragem é o atributo do **msExchangeHideFromAddressBook**. Este é um atributo de usuário adicionado pelo esquema do Exchange. Se o valor desse atributo é VERDADEIRO, o Exchange Server usa esse atributo para ocultar o contato da lista de endereços global do Outlook (GAL). Da mesma forma, se o valor desse atributo é VERDADEIRO, o Replicador de usuário não inclui o usuário na tabela AbUserEntry e esse usuário não estará nos arquivos do servidor de catálogo de endereços.

Você pode usar alguns bits de sinalizadores para definir um filtro a ser usado nos atributos do servidor de catálogo de endereços. Por exemplo, a presença de determinados bits de sinalizador pode identificar um atributo como um atributo de inclusão ou exclusão. O Replicador de usuários filtra os contactos que contêm um atributo de exclusão e filtra conteúdos que não têm um atributo de inclusão.

<div>


> [!WARNING]  
> Para obter mais informações sobre como filtrar o catálogo de endereços, consulte <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlets do servidor do catálogo de endereços no Lync Server 2013</A>e <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filtrar catálogo de endereços do Lync 2013</A>



</div>

Atualmente existem três filtros diferentes. A tabela a seguir lista esses filtros.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se definido, identifica um atributo necessário para um contato. O Replicador de usuário usa esse bit de sinalizador para filtrar os contatos que não contêm pelo menos um atributo necessário. O OuPathId é um atributo obrigatório, que sempre é definido. Portanto, pelo menos um dos outros necessários atributos devem ser definidos. Caso contrário, o contato (isto é, com valor do atributo OuPathId necessário) ainda não será gravado no banco de dados. Por exemplo, se <strong>telephoneNumber</strong> e <strong>TelefoneResidencial</strong> são definidos como atributos necessários, somente os contatos que têm pelo menos um desses atributos são gravados no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se definido, identifica um atributo de exclusão. O Replicador de usuário usa esse bit de sinalizador para filtrar os contactos que contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> é definido como um atributo de exclusão, contatos que têm este atributo não são gravados no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se definido, identifica um atributo de inclusão. O Replicador de usuário usa esse bit de sinalizador para filtrar os contactos que não contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> é definido como um atributo de inclusão, somente os contatos que têm este atributo são gravados no banco de dados.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se os bits de sinalizador 0x4000 (excluir atributo) e 0x8000 (incluir atributo) estão definidos, o bit 0x4000 substitui o bit 0x8000 e o contato é excluído.



</div>

Embora você possa filtrar o catálogo de endereços para incluir somente certos usuários, limitar as entradas não limita a capacidade de  outros usuários para entrar em contato com os usuários filtrados ou para ver seu status de presença. Os usuários sempre podem enviar manualmente mensagens instantâneas, iniciar chamadas ou encontrar os usuários que não estão no catálogo de endereços, digitando o nome completo de entrada de um usuário. Além disso, as informações de contato para um usuário também podem ser encontradas no Outlook.

Os registros de contato completo nos arquivos do catálogo de endereços permitem que você use o Lync Server para iniciar chamadas de email, telefone ou Enterprise Voice (ou seja, se o Enterprise Voice estiver habilitado no servidor) com usuários que não estão configurados para o início da sessão Protocol (SIP), algumas organizações preferem incluir apenas usuários habilitados para SIP nas entradas do servidor do catálogo de endereços. Você pode filtrar o catálogo de endereços para incluir somente os usuários habilitados para o SIP limpando o bit 0x800 na coluna **Sinalizadores** dos seguintes atributos obrigatórios: **mailNickname**, **telephoneNumber**, **homePhone** e **celular**. Você também pode filtrar o catálogo de endereços para incluir somente os usuários habilitados para SIP, definindo o 0x8000 (inclua o atributo) na coluna **Sinalizadores ** do atributo **msRTCSIP-PrimaryUserAddress **. Isso também ajuda a excluir as contas de serviço de arquivos de catálogo de endereços.

Depois de modificar a tabela AbAttribute, você pode atualizar os dados na tabela AbUserEntry executando o comando do cmdlet **Update-CsUserDatabase**. Após a conclusão da replicação UR, é possível atualizar o arquivo no repositório de arquivos do servidor de catálogo de endereços manualmente, executando o comando cmdlet **UpdateCsAddressBook**.

<div>


> [!NOTE]  
> O servidor front-end no qual o servidor do catálogo de endereços é colocado não é administrativamente configurável. Um é escolhido durante a implantação — normalmente, o primeiro servidor front-end implantado. No caso de falha, o serviço de catálogo de endereços mudará para outro servidor de front-end e não exigirá atenção administrativa.



</div>

<div>


> [!IMPORTANT]  
> Se você consolidou ou modificou sua infraestrutura de uma implantação de várias florestas ou de uma implantação pai/filho (como consolidar sua infraestrutura antes de migrar para o Lync Server), você pode descobrir que o download do serviço de catálogo de endereços e a consulta à Web do catálogo de endereços falham para alguns usuários. Quando em uma implantação que tinha vários domínios ou florestas, o atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> é preenchido nos objetos de usuário que estão apresentando o problema. O atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> deve ser definido como NULO nesses objetos para solucionar o problema.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

