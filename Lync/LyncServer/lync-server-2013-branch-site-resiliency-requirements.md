---
title: 'Lync Server 2013: requisitos de resiliência de site de filial'
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
ms.openlocfilehash: f1e8fb2cdbf2b9192411f74c5099930d8bd7d7a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisitos de resiliência de site de filial para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-25_

Este tópico ajudará a você preparar usuários para resiliência de site de filial e persistência da caixa postal, e também especifica os requisitos de hardware e software importantes.


<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparação de usuários da filial para resiliência de site de filial

Prepare os usuários para resiliência de site de filial definindo seu pool de registradores como o aparelho de filial persistente (SBA) ou servidor de filial persistente.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Atribuições do registrador avançado para usuários da filial

Independentemente da solução de resiliência de site de filial que você escolher, será necessário atribuir um registrador principal a cada usuário. Os usuários do site de filial devem sempre se registrar no site de filial, independentemente de o registrador residir no aparelho de filial persistente, no servidor de filial persistente ou no servidor autônomo do Lync Server 2013 Standard ou Enterprise Edition. Um registro de recurso de serviço (SRV) de sistema de nome de domínio (DNS) é necessário para que o cliente possa descobrir seu pool de Registrador. Se o aparelho de filial persistente ficar indisponível, é assim que os clientes do site de filial descobrirão automaticamente o registrador de backup.

Se um site de filial não tiver um servidor DNS, há duas maneiras alternativas para configurar a descoberta do aparelho de filial persistente ou servidor de filial persistente:

  - Configure a opção de DHCP 120 no servidor de protocolo DHCP para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de filial persistente ou servidor de filial persistente.

  - Configure o aparelho de filial persistente ou servidor de filial persistente para responder às consultas do DHCP 120.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Roteamento de voz para usuários de filial

É recomendável criar uma política separada de VoIP (Voice over Internet Protocol ) no nível do usuário para usuários em um site de filial. Essa política deve incluir uma rota primária que usa o aparelho de filial persistente ou o gateway de servidor de filial e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutada) no site central. Se a rota principal estiver indisponível, a rota de backup que usa um ou mais gateways do site central será utilizada. Desta forma, independentemente de onde o usuário estiver registrado, seja no Registrador Avançado do site de filial ou no pool de registradores de backup no site central, a política de VoIP do usuário sempre estará em vigor. Esta é uma consideração importante para cenários de failover. Por exemplo, se for necessário renomear o aparelho de filial persistente ou reconfigurar o aparelho de filial persistente para se conectar a um pool de registradores de backup no site central, você deverá mover os usuários do site da filial para o site central para a duração. (Para obter detalhes sobre como renomear ou reconfigurar um aparelho de filial persistente, consulte o [Apêndice B: gerenciando um aparelho de filial persistente no Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) na documentação de implantação.) Se esses usuários não tiverem políticas de VoIP em nível de usuário ou planos de discagem em nível de usuário, quando os usuários forem movidos para outro site, as políticas de VoIP no nível do site e os planos de discagem no nível do site central se aplicarão aos usuários por padrão, em vez das políticas e planos de discagem no nível de site do site de filial,. Neste cenário, a menos que as políticas de VoIP e planos de discagem de nível de site usados pelo pool de registradores de backup também possam ser aplicadas aos usuários do site de filial, suas chamadas falharão. Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmund, um plano de discagem com regras de normalização que precedam +1425 a todas as chamadas de 7 dígitos provavelmente não traduzirá chamadas de forma apropriada para estes usuários.

<div>


> [!IMPORTANT]  
> Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de utilização de telefone do PSTN à política do usuário do escritório da filial e atribuir rotas separadas para cada uma. A rota inicial, ou primária, direcionaria as chamadas para o gateway associado ao aparelho de filial persistente (SBA) ou ao servidor de filial; o segundo, ou backup, rota direcionaria chamadas para o gateway no site central. Ao direcionar chamadas, o SBA ou servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso do PSTN antes de tentar o segundo registro de uso.



</div>

Para ajudar a garantir que as chamadas de entrada para os usuários do site de filial chegarão aos usuários quando o gateway de filial ou o componente do Windows do site do aparelho de filial persistente não estiver disponível (o que aconteceria, por exemplo, se o aparelho ou ramificação de filial persistente o gateway estava desativado para manutenção), crie uma rota de failover no gateway (ou trabalhe com seu provedor de discagem direta interna) para redirecionar as chamadas de entrada para o pool de registradores de backup no site central. Daí, as chamadas serão roteadas sobre o link WAN para os usuários da filial. Garanta que a rota traduza os números para estar de acordo com o gateway PSTN ou outros formatos de número de telefone aceitos pelo ponto do tronco. Para obter detalhes sobre como criar uma rota de failover, consulte [Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Crie também planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial para normalizar chamadas de entrada. Se você tiver dois aparelhos de filial persistentes em um site de filial, você pode criar um plano de discagem no nível do site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.

<div>


> [!NOTE]  
> Para suportar o consumo dos recursos do site central pelos usuários de qualquer site de filial que se apoiem no site central para presença, conferência ou failover, é recomendável considerar cada usuário de site de filial como se estivesse registrado no site central. No momento, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um aparelho de filial persistente.



</div>

Também é recomendável criar um plano de discagem de nível de usuário e uma política de voz e atribuí-los a usuários do site de filial. Para obter detalhes, consulte [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [criar a política de roteamento VoIP para usuários de filial no Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) na documentação de implantação.

<div>

## <a name="routing-extension-numbers"></a>Números de extensão de roteamento

Ao preparar planos de discagem e políticas de voz para usuários de site de filial, certifique-se de incluir regras de normalização e regras de conversão que correspondam às cadeias de caracteres e formato de número usados no atributo msRTCSIP-line (ou line URI), de modo que as chamadas do Lync 2013 habilitadas entre Branch os usuários do site e os usuários do site central serão roteados corretamente, especialmente quando as chamadas devem ser reencaminhadas pela PSTN porque o link WAN não está disponível. Existem considerações especiais adicionais para números discados que contêm números de extensão, em vez de apenas números de telefone.

Regras de normalização e de tradução que correspondam a URIs de Linha que contêm um número de extensão, seja de forma exclusiva ou além de um número de telefone totalmente E.164, possuem requisitos adicionais. Esta seção descreve vários cenários de exemplo para rotear chamadas para URIs de Linha com um número de extensão.

Se sua organização não possui Números Fixos Virtuais (DID) configurados para usuários individuais e a URI de Linha de cada usuário está configurada *apenas* com um número de extensão, usuários internos podem ligar uns para os outros discando apenas um número de extensão. No entanto, é necessário configurar regras de normalização que possam se aplicar a chamadas a partir de um site de filial para um usuário do site central que correspondam a números de extensão.

Em um cenário onde o link WAN entre um site de filial e um site central esteja disponível, chamadas de usuários do site de filial para usuários do site central não exigem que a regra de normalização correspondente traduza o número porque a chamada não é roteada sobre o PSTN. Por exemplo:


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
<th>Padrão de número</th>
<th>Tradução</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Não traduz números de 5 dígitos</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 não é traduzido</p></td>
</tr>
</tbody>
</table>


Você também deve acomodar números de extensão para cenários específicos, como quando o link WAN entre um site de filial e o site central está indisponível e um chamada de um site de filial deve ser roteada através do PSTN. Durante uma interrupção da WAN, se um usuário do site de filial ligar para um usuário do site central discando apenas sua extensão, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo do usuário do site central. Se a URI de Linha contiver o número de telefone completo da sua empresa e o número de extensão único do usuário em vez de um número de telefone completo que seja único para o usuário, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo da empresa no lugar. Por exemplo:


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
<th>Tradução</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduz números de 5 dígitos para o número de telefone e extensão de um usuário</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; Ext = $1</p></td>
<td><p>10001 é traduzido como +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Traduz números de 5 dígitos para o número de telefone da sua empresa e a extensão de um usuário</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100; Ext = $1</p></td>
<td><p>10001 é traduzido como +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


Neste cenário, se o ponto do tronco que trata o re-roteamento para o PSTN não suportar os números de extensão, a regra de tradução de saída também deve remover o número de extensão. Por exemplo:


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
<th>Tradução</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Remove a extensão dos números de telefone com extensões</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+14255550123;ext=10001 é traduzido como +14255550123</p></td>
</tr>
</tbody>
</table>


Independente da disponibilidade de um link WAN, se sua organização não possuir números DID configurados para usuários individuais e a URI de Linha para um usuário contiver o número de telefone da sua empresa e o número de extensão único do usuário, você deve configurar a URI de Linha do número de telefone da sua empresa com um número que seja alcançável pelo ponto do tronco ou gateway PSTN no site da filial. Você também deve configurar a URI de Linha do número de telefone da sua empresa para incluir sua própria extensão única para chamadas a serem roteadas para este número.

Para obter detalhes sobre chamadas de um usuário do site central para um usuário do site de filial quando o link WAN entre os sites está indisponível, consulte Preparação para Persistência de Caixa Postal, posteriormente neste tópico. Para obter detalhes sobre planos de discagem e regras de normalização, incluindo outras regras de amostra, consulte [Dial Plans and Normalization Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento e [configurar planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md) na documentação de implantação. Para obter detalhes sobre as regras de conversão de saída, consulte [regras de conversão no Lync server 2013](lync-server-2013-translation-rules.md) na documentação de planejamento e [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Preparação para persistência de caixa postal

A Unificação de mensagens (UM) do Exchange geralmente é instalada em um site central e não em sites de filial. Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo se o link WAN entre o site da filial e o site central estiver indisponível. Como resultado, a configuração do URI de linha para o número de telefone do atendedor automático do UM do Exchange que fornece caixa postal para usuários do site de filial requer considerações especiais, além das regras de política de voz, plano de discagem e normalização aplicáveis a essa caixa postal série.

Os aparelhos de ramificação persistente (SBAs) e os servidores de filial persistente fornecem sustentabilidade da caixa postal para usuários de filial durante uma interrupção da WAN. Especificamente, se você estiver usando um aparelho de filial persistente ou servidor de filial persistente e a WAN ficar indisponível, o servidor de filial SBA ou persistente redireciona novamente as chamadas não atendidas pela PSTN para UM do Exchange no site central. Com um servidor de filial SBA ou persistente, os usuários também podem recuperar mensagens de caixa postal através da PSTN durante uma interrupção da WAN. Por fim, durante uma interrupção da WAN, o aparelho de filial persistente ou o servidor de filial persistente enfileira as notificações de chamadas perdidas e, em seguida, carrega-as para o servidor de UM do Exchange quando a WAN é restaurada. Para ajudar a garantir que o encaminhamento de caixa postal é resistente, certifique-se de adicionar uma entrada para o FQDN do pool de sites central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de filial persistente. Do contrário, a resolução do DNS pode ultrapassar o tempo se não houver um servidor DNS no site da filial.

Recomendamos seguir as configurações a seguir para a persistência de caixa postal para usuários de filiais:

  - Um administrador do Microsoft Exchange deve configurar o atendedor automático da UM do Exchange para aceitar apenas mensagens. Esta configuração desabilita todas as outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador e limita o AA a aceitar apenas mensagens. Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado para rotear a chamada para um operador.

  - O administrador do Lync Server deve obter o número de telefone AA e usar esse número de telefone como o número de **atendedor automático do um do Exchange** nas configurações de reencaminhamento de caixa postal para o aparelho de filial persistente ou servidor de filial.

  - O administrador do Lync Server deve obter o número de telefone de acesso do assinante da UM do Exchange e usar esse número como o número de **acesso do assinante** nas configurações de reencaminhamento de caixa postal para o aparelho de filial persistente ou servidor de filial persistente.

  - O administrador do Lync Server deve configurar UM do Exchange para que apenas um plano de discagem seja associado a todos os usuários da filial que precisam acessar a caixa postal durante uma interrupção da WAN.

  - Quando o link WAN está indisponível, as chamadas para usuários do site da filial podem ser roteadas para a caixa postal da UM (Unified Messaging) do Exchange, mas somente se a política de Voz aplicada à chamada especificar um número de telefone de caixa postal que seja único e não inclua um número de extensão.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware e software para resiliência de site de filial

Os requisitos de hardware e software variam, dependendo da sua solução de resiliência.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para Aparelhos de Filial Persistente

O hardware e o software necessários estão integrados ao aparelho de filial persistente. No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter endereços IP clientes; do contrário, quando a concessão do DHCP expirar, os clientes não terão conectividade IP.

Se os servidores DNS corporativos estiverem localizados somente nos sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma interrupção da WAN e, portanto, a descoberta do Lync Server que usa o registro de recurso DNS SRV (serviço (SRV) falhará. Para garantir o re-roteamento imediato durante uma interrupção da WAN, registros DNS devem ser armazenados em cache no site da filial. Se o roteador da filial for compatível, ative o cache do DNS. Ou você pode implantar um servidor DNS na filial. Pode ser um servidor autônomo ou uma versão do aparelho de filial persistente que ofereça suporte a recursos DNS. Para obter detalhes, entre em contato com seu provedor de aparelho de filial persistente.

<div>


> [!NOTE]  
> Não é necessário ter um controlador de domínio no site da filial. O aparelho de filial persistente autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.



</div>

Os clientes do Lync podem descobrir o Lync Server usando a opção de DHCP 120 (opção de registrador SIP). Ela pode ser configurada em uma de duas formas:

  - Configure o servidor DHCP no site de filial para responder às consultas do DHCP 120, que retornam o FQDN do registrador no aparelho de filial persistente ou servidor de filial persistente.

  - Ative o Lync Server DHCP. Quando estiver ativado, o registrador do Lync Server responderá às consultas de opção 120 de DHCP. Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente da Opção 120 do DHCP.

Além disso, para sites de filial maiores, que possuem várias sub-redes, agentes de retransmissão DHCP devem estar habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).

Por fim, os usuários do site de filial devem ser configurados para o Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificada apropriado.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisitos para Servidores de Filial Persistente

Os requisitos para servidores de filial persistentes são os mesmos dos requisitos para um servidor front-end. Para obter detalhes, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de planejamento.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisitos para implantações de site de filial do Lync Server em larga escala

Para obter detalhes, consulte [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

