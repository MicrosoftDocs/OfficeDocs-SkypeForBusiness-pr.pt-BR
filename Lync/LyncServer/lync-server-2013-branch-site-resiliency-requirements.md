---
title: 'Lync Server 2013: Requisitos de resiliência do site da filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f146f2c358e6eb6718aa60f8a51106430e6a4a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisitos de resiliência do site da filial para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-25_

Este tópico ajudará você a preparar os usuários para resiliência do site de filial e persistência da caixa postal. Ele também especifica os requisitos importantes de hardware e software.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência do site de filial

Prepare os usuários para a resiliência de site de filial definindo o pool registrador como o aparelho de ramificação sobreviventes (SBA) ou o servidor de ramificação sobreviventes.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Atribuições do Registrador Avançado para usuários da filial

Independentemente da solução de resiliência de site de filial escolhida, será necessário atribuir um Registrador Avançado primário a cada usuário. Os usuários do site de ramificação sempre devem se registrar no registrador de site, independentemente de o registrador residir na ramificação, servidor de ramificação sobreviventes ou servidor autônomo do Lync Server 2013 Standard ou Enterprise Edition. Um registro DNS (Sistema de Nomes de Domínio) de recurso de serviços (SRV) é necessário para que o cliente possa descobrir o seu pool de Registradores Avançados. Se o aparelho de ramificação sobreviventes ficar indisponível, é como os clientes do site de filiais detectam automaticamente o registrador de backup.

Se um site de filial não tiver um servidor DNS, existem duas maneiras alternativas para configurar a descoberta do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes:

  - Configure a opção de DHCP 120 no servidor DHCP (Dynamic Host Configuration Protocol) para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes.

  - Configure o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes para responder às consultas de DHCP 120.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política VoIP separada em nível de usuário para os usuários de um site de filial. Essa política deve incluir uma rota primária que usa o aplicativo de ramificação ou o gateway de servidor de ramificação sobreviventes e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutada) no site central. Se a rota principal não estiver disponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Dessa forma, independentemente de onde o usuário estiver registrado — seja no Registrador Avançado do site de filial ou no pool de Registradores Avançados de backup no site central — a política VoIP do usuário estará sempre em vigor. Essa é uma consideração importante para cenários de failover. Por exemplo, se precisar renomear o aparelho de ramificação sobreviventes ou reconfigurar o aparelho de ramificação sobreviventes para se conectar a um pool de registradores de backup no site central, você deverá mover os usuários do site para o site central durante a duração. (Para obter detalhes sobre como renomear ou reconfigurar um aparelho de ramificação sobreviventes, consulte o [Apêndice B: gerenciando um aparelho de ramificação sobreviventes no Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) na documentação de implantação.) Se esses usuários não tiverem políticas de VoIP em nível de usuário ou planos de discagem em nível de usuário, quando os usuários forem movidos para outro site, as políticas de VoIP no nível do site e os planos de discagem no nível do site central se aplicam aos usuários por padrão, em vez de políticas de VoIP no nível de site e de planos de discagem Nesse cenário, a menos que as políticas VoIP e os planos de discagem em nível de site usados pelo pool de Registradores Avançados de backup também possam ser aplicados aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmond, um plano de discagem com regras de normalização que acrescentem o prefixo +1425 a todas as chamadas de 7 dígitos provavelmente não converterá as chamadas de forma apropriada para esses usuários.

<div>


> [!IMPORTANT]  
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de uso do telefone PSTN à política do usuário do escritório da filial e atribuir rotas separadas a cada um deles. A rota inicial ou primária faria chamadas para o gateway associado à ferramenta de ramificação (SBA) ou ao servidor de ramificação sobreviventes. a rota de segundo, ou backup, direcionaria chamadas para o gateway no site central. Ao direcionar as chamadas, o SBA ou o servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso PSTN, antes de tentar o segundo registro.



</div>

Para ajudar a garantir que as chamadas recebidas para os usuários do site de ramificação cheguem a esses usuários quando o gateway da ramificação ou o componente do Windows do site do aparelho de ramificação sobreviventes estiver indisponível (o que aconteceria, por exemplo, se a ramificação ou ramificação sobreviventes pode ser retentada o gateway foi desativado para manutenção), crie uma rota de failover no gateway (ou trabalhe com o seu provedor de discagem direta) para redirecionar as chamadas de entrada para o pool de registradores de backup no site central. A partir desse local, as chamadas serão encaminhadas através do link WAN para os usuários da filial. A rota deverá converter os números para que fiquem em conformidade com o gateway PSTN ou outros formatos de número de telefone aceitos pelo par de tronco. Para obter detalhes sobre como criar uma rota de failover, consulte [Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Além disso, crie planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial a fim de normalizar as chamadas de entrada. Se você tiver dois aparelhos de ramificação sobreviventes em um site de filial, poderá criar um plano de discagem em nível de site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.

<div>


> [!NOTE]  
> Para contabilizar o consumo de recursos do site central pelos usuários de um site de filial que dependam do site central para fins de presença, conferência ou failover, é recomendável considerar cada usuário do site de filial como se estivesse registrado no site central. No momento, não há limites quanto ao número de usuários de sites de filiais, incluindo usuários registrados em um aparelho de ramificação sobreviventes.



</div>

Também é recomendável criar um plano de discagem e uma política de voz em nível de usuário, e atribuí-los aos usuários do site de filial. Para obter detalhes, consulte [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [criar a política de roteamento de VoIP para usuários de ramificação no Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) na documentação de implantação.

<div>

## <a name="routing-extension-numbers"></a>Roteamento de números de ramal

Ao preparar planos de discagem e políticas de voz para usuários de site de ramificação, certifique-se de incluir regras de normalização e regras de tradução que correspondam às cadeias de caracteres e o formato de número usados no atributo msRTCSIP-linha (ou URI de linha) para que as chamadas do Lync 2013 sejam habilitadas entre Branch os usuários do site e os usuários do site central serão roteados corretamente, principalmente quando as chamadas devem ser redirecionadas pelo PSTN porque o link de rede de longa distância não está disponível. Além disso, há considerações especiais para números discados que contêm números de ramal, e não apenas números de telefone.

As regras de normalização e de conversão que fazem a correspondência das URIs de Linha que contêm um número de ramal, exclusivamente ou além de um número de telefone E.164 completo, têm requisitos adicionais. Esta seção descreve vários cenários de exemplo para encaminhar chamadas para URIs de Linha com um número de ramal.

Se a sua organização não tiver números de telefone de Discagem Direta Interna (DDI) configurados para usuários individuais, e a URI da Linha de cada usuário estiver configurada *apenas* com um número de ramal, os usuários internos poderão ligar uns para os outros discando apenas um número de ramal. No entanto, é necessário configurar regras de normalização aplicáveis às chamadas de um usuário do site de filial para outro do site central, que façam a correspondência dos números de ramal.

Em um cenário em que o link WAN entre um site de filial e um site central esteja disponível, as chamadas de usuários do site de filial para os do site central não exigirão que a regra de normalização de correspondência converta o número porque a chamada não é encaminhada através da PSTN. Por exemplo:


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome da regra</th>
<th>Descrição</th>
<th>Padrão do número</th>
<th>Conversão</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Não converte números de 5 dígitos</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 não é convertido</p></td>
</tr>
</tbody>
</table>


Você também deve acomodar números de ramal para cenários específicos, como, por exemplo, quando o link WAN entre um site de filial e o site central não está disponível, e uma chamada de um site de filial deve ser encaminhada através da PSTN. Durante uma interrupção da WAN, se um usuário do site de filial ligar para outro do site central discando apenas seu ramal, será necessário ter uma regra de conversão de saída que adicione o número de telefone completo do usuário do site central. Se a URI da Linha do usuário contiver o número de telefone completo da sua organização e o número de ramal exclusivo do usuário, em vez de um número de telefone completo que seja exclusivo do usuário, será necessário ter uma regra de conversão de saída que adicione o número de telefone completo da organização. Por exemplo:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Padrão de correspondência</th>
<th>Conversão</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Converte números de 5 dígitos no número de telefone e no ramal do usuário</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550123;ext=$1</p></td>
<td><p>10001 é convertido em +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Converte números de 5 dígitos no número de telefone da organização e no ramal do usuário</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550100;ext=$1</p></td>
<td><p>10001 é convertido em +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


Neste cenário, se o par do tronco que trata do reencaminhamento para a PSTN não aceitar números de ramal, a regra de conversão de saída também deverá remover o número do ramal. Por exemplo:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Padrão de correspondência</th>
<th>Conversão</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Remove o ramal dos números de telefone com ramais</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 é convertido em +14255550123</p></td>
</tr>
</tbody>
</table>


Independentemente de um link WAN estar ou não disponível, se a sua organização não tiver números DDI configurados para os usuários individuais, e a URI da Linha de um usuário contiver o número de telefone da organização e o número do ramal exclusivo do usuário, você deverá configurar a URI da Linha do número de telefone da organização com um número que possa ser acessado pelo par do tronco ou pelo gateway PSTN no site de filial. Você também deve configurar a URI da Linha do número de telefone da organização para incluir seu próprio ramal exclusivo de modo que as chamadas sejam encaminhadas para esse número.

Para obter detalhes sobre chamadas de um usuário do site central para um usuário do site da filial quando o link de WAN entre os sites não estiver disponível, consulte "preparando para a imsustentabilidade da caixa postal" mais adiante neste tópico. Para obter detalhes sobre planos de discagem e regras de normalização, incluindo outras regras de amostra, consulte [planos de discagem e regras de normalização no Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento e [Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md) na documentação de implantação. Para obter detalhes sobre as regras de conversão de saída, consulte [regras de tradução no Lync server 2013](lync-server-2013-translation-rules.md) na documentação de planejamento e [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência da caixa postal

A UM (Unificação de mensagens) do Exchange geralmente é instalada apenas em um site central e não em sites de filiais. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo que o link WAN entre o site de filial e o central não esteja disponível. Como resultado, a configuração do URI de linha do número de telefone do atendedor automático do Exchange UM que forneça a caixa postal para os usuários do site de ramificação exige considerações especiais, além da política de voz, do plano de discagem e das regras de normalização aplicáveis a essa caixa postal tempo.

Os appliances de ramificação sobreviventes (SBAs) e os servidores de filiais sobreviventes fornecem sustentabilidade da caixa postal para usuários de filiais durante uma falha de WAN. Especificamente, se você estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes e a WAN ficar indisponível, o servidor de ramificação SBA ou sobreviver redirecionará chamadas não atendidas pela PSTN para o Exchange UM no site central. Com um servidor de ramificação SBA ou sobreviventes, os usuários também podem recuperar mensagens de caixa postal por meio da PSTN durante uma falha de WAN. Por fim, durante uma falha de WAN, o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes enfileira notificações de chamada perdida e, em seguida, carrega-as para o servidor do Exchange UM quando a WAN é restaurada. Para ajudar a garantir que o redirecionamento de caixa postal seja resistente, certifique-se de adicionar uma entrada para o FQDN do pool de site central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de ramificação sobreviventes. Caso contrário, o tempo limite da resolução DNS poderá expirar se não houver um servidor DNS no site de filial.

Recomendamos definir as configurações a seguir para a persistência da caixa postal dos usuários do site de filial:

  - Um administrador do Microsoft Exchange deve configurar o atendedor automático do Exchange UM para aceitar somente mensagens. Essa configuração desabilita todas as outras funcionalidades genéricas, como a transferência para um usuário ou a transferência para um operador, e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado a fim de encaminhar a chamada para um operador.

  - O administrador do Lync Server deve levar o número de telefone AA e usar esse número de telefone como o número de **atendedor automático de um do Exchange** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação ou servidor de ramificação sobreviventes.

  - O administrador do Lync Server deve obter o número de telefone de acesso do assinante do Exchange UM e usar esse número como o número de **acesso do assinante** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.

  - O administrador do Lync Server deve configurar o UM do Exchange para que apenas um plano de discagem esteja associado a todos os usuários da ramificação que precisam acessar a caixa postal durante uma falha de WAN.

  - Quando o link WAN não está disponível, as chamadas para os usuários do site de filial poderão ser encaminhadas para a caixa postal de UM (Unificação de Mensagens) do Exchange do usuário, mas somente se a política de voz aplicada à chamada especificar um número de telefone de caixa postal que seja exclusivo e não inclua um número de ramal.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de sites de filial

Os requisitos de hardware e software variam, dependendo da solução de resiliência.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários estão integrados ao aparelho de ramificação sobreviventes. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter os endereços IP de clientes; caso contrário, quando a concessão de DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS da empresa estiverem localizados somente em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma falha de WAN e, portanto, a descoberta do Lync Server que usa o SRV (registro de recurso de serviço) DNS falhará. Para garantir o redirecionamento de prompt durante uma falha de WAN, os registros DNS devem ser armazenados em cache no site da filial. Se o roteador de ramificação oferecer suporte, ative o cache de DNS. Ou você pode implantar um servidor DNS na ramificação. Isso pode ser um servidor autônomo ou uma versão do aparelho de ramificação sobreviventes que ofereça suporte a recursos de DNS. Para obter detalhes, entre em contato com seu provedor de aparelho de ramificação sobreviventes.

<div>


> [!NOTE]  
> Não é necessário ter um controlador de domínio em um site de filial. O aparelho de ramificação sobreviventes autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.



</div>

Os clientes do Lync podem descobrir o Lync Server usando a opção de DHCP 120 (opção de registrador de SIP). Essa opção pode ser configurada de uma de destas duas maneiras:

  - Configure o servidor DHCP no site de filial para responder a consultas DHCP 120, que retornam o FQDN do registrador na ramificação da ramificação sobreviventes ou do servidor de ramificação sobreviventes.

  - Ative o DHCP do Lync Server. Quando essa opção estiver ativada, o registrador do Lync Server responderá às consultas de opção de DHCP 120. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente das Opções 120 do DHCP.

Além disso, para sites de filial maiores, com várias sub-redes, agentes de retransmissão DHCP devem ser habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filiais devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificado apropriado.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para servidores de filiais sobreviventes são os mesmos dos requisitos para um servidor front-end. Para obter detalhes, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de planejamento.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisitos para implantações em filiais do servidor do Lync Server em toda a escala

Para obter detalhes, consulte [determinando os requisitos de infraestrutura do Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

