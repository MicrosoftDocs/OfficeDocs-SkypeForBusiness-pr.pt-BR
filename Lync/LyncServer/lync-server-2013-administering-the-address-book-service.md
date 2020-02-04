---
title: 'Lync Server 2013: administrando o serviço de catálogo de endereços'
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
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Administrar o serviço de catálogo de endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

Como parte da implantação do Lync Server, Enterprise Edition ou do servidor Standard Edition, o serviço de catálogo de endereços é instalado por padrão. O banco de dados usado pelo serviço de catálogo de endereços – RTCab – é criado no SQL Server (para Enterprise Edition, esse é o servidor SQL Server de back-end; para o servidor Standard Edition, o SQL Server posicionado).

<div>


> [!NOTE]  
> Para obter informações sobre como usar o <STRONG>ADSI Edit</STRONG> para editar atributos de objeto dos serviços de domínio Active Directory, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Para obter informações sobre uma ferramenta no kit de recursos especificamente para o serviço de catálogo de endereços, consulte <A href="http://go.microsoft.com/fwlink/?linkid=330429">Ferramentas do Microsoft Lync Server 2013 Resource Kit</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalização do número de telefone do servidor do catálogo de endereços

O Lync Server exige números de telefone padrão RFC 3966/E. 164. Para usar números de telefone não estruturados ou formatados de forma inconsistente, o Lync Server dependerá do servidor do catálogo de endereços para processar os números de telefone antes que eles sejam entregues às regras de normalização. Quando um número de telefone é usado no catálogo de endereços e a regra de normalização é aplicada, os clientes, como o Lync Phone Edition e o Lync Mobile, podem usar esses números normalizados.

As regras de normalização usadas nas versões anteriores podem não funcionar corretamente sem alguns ajustes. Como o espaço em branco e os caracteres não obrigatórios são removidos antes das regras de normalização, se a sua expressão Regex estiver procurando por um traço ou outro caractere que tenha sido removido, sua regra de normalidade poderá falhar. Você deve revisar suas regras de normalização para garantir que elas não estejam procurando por esses caracteres não obrigatórios, ou que a regra possa ser reprovada e continue no caso de o personagem não estar presente onde a regra prevê que ela será.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Duplicador de usuários e servidor de catálogo de endereços

O servidor de catálogo de endereços usa os dados fornecidos pelo duplicador de usuários para atualizar as informações que ele inicialmente obtém na GAL (lista de endereços global). O duplicador de usuários grava os atributos dos serviços de domínio Active Directory para cada usuário, contato e grupo na tabela AbUserEntry do banco de dados e o servidor do catálogo de endereços sincroniza os dados do usuário do banco de dados em arquivos no repositório de arquivos do servidor do catálogo de endereços e na RTCab do banco de dados do catálogo de endereços. O esquema para a tabela AbUserEntry usa duas colunas, **userguid** e **UserData**. **Userguid** é a coluna de índice e contém o GUID de 16 bytes do objeto do Active Directory. **UserData** é uma coluna de imagem que contém todos os atributos dos serviços de domínio do Active Directory mencionados anteriormente para esse contato.

O duplicador de usuários determina quais atributos do Active Directory gravar lendo uma tabela de configuração localizada na mesma instância baseada no SQL Server como a tabela AbUserEntry. A tabela AbAttribute contém três colunas, **ID**, **nome**, **sinalizadores**e **habilitar**. A tabela é criada durante a configuração do banco de dados. Se a tabela AbAttribute estiver vazia, o usuário duplicador ignorará sua lógica de processamento de tabela AbUserEntry. Os atributos do servidor de catálogo de endereços são dinâmicos e são recuperados da tabela AbAttribute, que é inicialmente escrita pelo servidor de catálogo de endereços quando o servidor do catálogo de endereços é ativado.

A ativação do servidor do catálogo de endereços preenche a tabela AbAttribute com os valores mostrados na tabela a seguir.


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
<th>Informa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>especificado</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>SN</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Título</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Empresa</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>254</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11:00</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>0,13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Mensageiro</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>GroupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Partamentais</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>16</p></td>
<td><p>Descrição</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>dezoito</p></td>
<td><p>Gerente</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>pol</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>cedido</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>EntryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Os números na coluna **ID** devem ser exclusivos e nunca devem ser reutilizados. Além disso, manter os valores de ID em 256 poupa espaço nos arquivos de saída gravados pelo servidor de catálogo de endereços. No entanto, o valor de ID máximo é 65535. A coluna **Name** corresponde ao nome de atributo do Active Directory que o replicador do usuário deve colocar na tabela AbUserEntry para cada contato. O valor na coluna **sinalizadores** é usado para definir o tipo de atributo. Os seguintes tipos de atributos do servidor de catálogo de endereços são reconhecidos pelo replicador do usuário, indicado pelo byte inferior do valor na coluna **sinalizadores** .


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
<td><p>Um atributo String. O duplicador de usuários converte esse tipo em UTF-8 antes de armazená-lo na tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Um atributo binário. O duplicador de usuários armazena isso no blob sem nenhuma conversão.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Um atributo String, mas está incluído apenas se o valor do atributo começa &quot;com Tel&quot;:. Isso é principalmente para atributos de cadeia de caracteres de vários valores, especificamente <strong>proxyAddresses</strong>. Nesse caso, o servidor de catálogo de endereços está interessado apenas em entradas <strong>proxyAddresses</strong> que &quot;começam com&quot;Tel:. Portanto, no que se está economizando espaço, o duplicador de usuários armazena apenas as entradas &quot;que começam&quot;com Tel:.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Um atributo de cadeia de caracteres booliano, que se verdadeiro faz com que o duplicador de usuários não inclua esse contato na tabela AbUserEntry. Se falso, ele fará com que o duplicador de usuários inclua os atributos para esse contato na tabela AbUserEntry, mas não o atributo específico com esse sinalizador. Esse é outro tipo de caso especial que é principalmente para o atributo <strong>msExchHideFromAddressLists</strong> .</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Um atributo String, mas está incluído apenas se o valor do atributo começa &quot;com SMTP&quot; : e inclui &quot; @ &quot; o símbolo.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Um atributo String, mas está incluído apenas se o valor do atributo começa com &quot;Tel:&quot; ou &quot;SMTP:&quot; e inclui o &quot; @ &quot; símbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Se definido, é um atributo de valores múltiplos que pode aparecer mais de uma vez para cada contato.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Se definido, identifica o atributo de nome da conta de usuário de email de um contato. O servidor de catálogo de endereços usa esse sinalizador para identificar o valor de atributo a ser mostrado na entrada do log de eventos de normalização do telefone.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se definido, identifica um atributo obrigatório para um contato. O servidor de catálogo de endereços inclui um usuário na tabela AbUserEntry somente se houver um valor para esse atributo no Active Directory. Se houver mais de um atributo obrigatório, apenas um deles será necessário para incluir um valor para incluir o usuário na tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Se definido, o servidor do catálogo de endereços sempre normalizará o valor desse atributo.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Se definido, o servidor do catálogo de endereços usará o número normalizado do <strong>proxyAddresses</strong>, se a configuração de CMS do <strong>UseNormalizationRules</strong> for falsa; caso contrário, ele se comporta como quando o bit do sinalizador é 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços não inclui objetos na tabela AbUserEntry que têm esse valor para o atributo especificado. Por exemplo, se o atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tiver esse conjunto de bits de sinalizador, os contatos que tiverem esse atributo não serão gravados no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se definido, o servidor de catálogo de endereços não inclui objetos na tabela AbUserEntry que não têm esse valor para o atributo especificado. Se os bits de sinalizador 0x4000 e 0x8000 estiverem definidos em um objeto, o atributo com o valor de bit de sinalizador definido como 0x4000 terá precedência, e o objeto será excluído da tabela AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Se definido, representa um objeto de grupo. O duplicador de usuários usa esse bit de sinalizador para incluir contatos com o atributo <strong>GroupType</strong> cuja presença indica um grupo (por exemplo, uma lista de distribuição ou um grupo de segurança).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Se definido, o duplicador de usuários usa esse bit de sinalizador para incluir esse atributo em arquivos de servidor de catálogo de endereços específicos do dispositivo (ou seja, arquivos com extensão. dabs).</p></td>
</tr>
</tbody>
</table>


Em versões anteriores do Lync Server, ao aplicar uma alteração ao Active Directory, o administrador seria obrigado a executar **Update-CSUserDatabase** e **Update-CSAddressBook** cmdlets do Windows PowerShell para persistir a alteração para o banco de dados de usuários do Lync Server e para RTCab o banco de dados imediatamente. No Lync Server 2013, o duplicador de usuários do Lync Server atenderá as alterações do Active Directory e atualizará o banco de dados de usuários do Lync Server com base em um intervalo configurado. O duplicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook. Se a consulta da Web do catálogo de endereços estiver habilitada, as alterações serão refletidas nos resultados da pesquisa pelos clientes do Lync. Os administradores só precisarão executar Update-CSAddressBook se o download do arquivo do catálogo de endereços estiver habilitado.

<div>


> [!NOTE]  
> Por padrão, o duplicador de usuários do Lync Server é executado automaticamente a cada 5 minutos. Você pode configurar esse intervalo usando Set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrando o catálogo de endereços

Os usuários preenchidos nos arquivos do servidor do catálogo de endereços podem ser controlados com base em determinados atributos dos serviços de domínio Active Directory listados na tabela AbAttribute. Um atributo desse tipo usado para a filtragem é o atributo **msExchangeHideFromAddressBook** . Esse é um atributo de usuário adicionado pelo esquema do Exchange. Se o valor desse atributo for TRUE, o Exchange Server usará esse atributo para ocultar o contato da GAL (lista de endereços global) do Outlook. Da mesma forma, se o valor desse atributo for TRUE, o Duplicador do usuário não incluirá esse usuário na tabela AbUserEntry e esse usuário não estará nos arquivos do servidor do catálogo de endereços.

Você pode usar alguns bits de sinalizador para definir um filtro a ser usado nos atributos do servidor do catálogo de endereços. Por exemplo, a presença de determinados bits de sinalizador pode identificar um atributo como um atributo Include ou um atributo Exclude. O duplicador de usuários filtra os contatos que contêm um atributo de exclusão e filtra os contém que não contêm um atributo include.

<div>


> [!WARNING]  
> Para obter mais informações sobre como filtrar o catálogo de endereços, consulte <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">cmdlets do servidor do catálogo de endereços no Lync Server 2013</A>e <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filtrar catálogo de endereços do Lync 2013</A>



</div>

Atualmente, há três filtros diferentes. A tabela a seguir lista esses filtros.


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
<td><p>Se definido, identifica um atributo obrigatório para um contato. O duplicador de usuários usa este bit de sinalizador para filtrar os contatos que não contêm pelo menos um atributo obrigatório. O OuPathId é um atributo obrigatório, que é sempre definido. Portanto, pelo menos um dos outros atributos obrigatórios deve ser definido. Caso contrário, o contato (ou seja, com o valor do atributo obrigatório OuPathId) ainda não será gravado no banco de dados. Por exemplo, se <strong>telephoneNumber</strong> e <strong>homePhone</strong> forem definidos como atributos obrigatórios, somente os contatos que tiverem pelo menos um desses atributos serão gravados no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se definido, identifica um atributo de exclusão. O duplicador de usuários usa esse sinal bit para filtrar os contatos que contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> for definido como um atributo Exclude, os contatos que tiverem esse atributo não serão gravados no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se definido, isso identifica um atributo include. O duplicador de usuários usa este bit de sinalizador para filtrar os contatos que não contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> for definido como um atributo Include, somente os contatos que tiverem esse atributo serão gravados no banco de dados.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se os bits de sinalizador 0x4000 (Exclude Attribute) e 0x8000 (include Attribute) estiverem definidos, o bit 0x4000 substituirá o bit 0x8000 e o contato será excluído.



</div>

Embora você possa filtrar o catálogo de endereços para incluir apenas determinados usuários, limitar as entradas não limita a capacidade dos outros usuários de entrar em contato com os usuários filtrados ou ver o status de presença deles. Os usuários sempre podem localizar, enviar manualmente mensagens de chat ou iniciar manualmente chamadas para usuários que não estão no catálogo de endereços inserindo um nome de entrada completo do usuário. Além disso, as informações de contato para um usuário também podem ser encontradas no Outlook.

Embora tenha registros de contatos completos nos arquivos do catálogo de endereços, você pode usar o Lync Server para iniciar emails, telefones ou chamadas de voz corporativas (ou seja, se o Enterprise Voice estiver habilitado no servidor) com usuários que não estão configurados para o início da sessão Protocol (SIP), algumas organizações preferem incluir somente usuários habilitados para SIP nas entradas do servidor de catálogo de endereços. Você pode filtrar o catálogo de endereços para incluir somente usuários habilitados para SIP, desmarcando o bit 0x800 na coluna **sinalizadores** dos seguintes atributos obrigatórios: **mailNickname**, **telephoneNumber**, **homePhone**e **celular**. Você também pode filtrar o catálogo de endereços para incluir somente usuários habilitados para SIP definindo o 0x8000 (include Attribute) na coluna **flags** do atributo **msRTCSIP-PrimaryUserAddress** . Isso também ajuda a excluir contas de serviço dos arquivos do catálogo de endereços.

Depois de modificar a tabela AbAttribute, você pode atualizar os dados na tabela AbUserEntry executando o comando **Update-CsUserDatabase** do cmdlet Update. Após a conclusão da replicação UR, você pode atualizar o arquivo no repositório de arquivos do servidor do catálogo de endereços executando manualmente o comando cmdlet **UpdateCsAddressBook** .

<div>


> [!NOTE]  
> O servidor front-end no qual o servidor do catálogo de endereços não é configurado administrativamente. Um é escolhido durante a implantação — geralmente, o primeiro servidor de front-end implantado. Em caso de falha, o serviço de catálogo de endereços passará para outro servidor front-end e não exigirá atenção administrativa.



</div>

<div>


> [!IMPORTANT]  
> Se você consolidou ou modificou sua infraestrutura de uma implantação de várias florestas ou de uma implantação pai/filho (como consolidar sua infraestrutura antes de migrar para o Lync Server), talvez descubra que o download do serviço de catálogo de endereços e a consulta à Web do catálogo de endereços falham para alguns usuários. Quando em uma implantação que tinha vários domínios ou florestas, o atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> é preenchido nos objetos de usuário que estão apresentando o problema. O atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> deve ser definido como NULL nesses objetos para resolver o problema.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

