---
title: Exibir aplicativos de servidor do Idioma de Processamento SIP da Microsoft
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Exibir aplicativos de servidor do Idioma de Processamento SIP da Microsoft (MSPL) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-09-26_

Um aplicativo de servidor Microsoft SIP Processing Language (MSPL) é um aplicativo somente de script que usa uma linguagem de script em vez da API do Microsoft Lync 2010. O MSPL fornece controle mais granular sobre filtragem e comportamentos de proxy, além de um recurso para a expedição de mensagens específicas para aplicativos SIP baseados em transações. MSPL é usado especificamente para filtrar e rotear mensagens SIP. Os aplicativos do MSPL são executados no mesmo processo do módulo userservices, enquanto um programa baseado na API do Lync 2010 é executado em um processo separado.

Você pode usar a página de **aplicativo do servidor** no grupo **Topology** do painel de controle do Lync Server para ver uma lista de aplicativos do MSPL Server que são executados em servidores front-end no ambiente do Lync Server 2013. A lista mostra os scripts que estão disponíveis para cada pool, bem como se eles estão habilitados ou críticos. Os scripts são executados na ordem em que são listados.

Esses scripts incluem o seguinte:

  - O ClientVersionFilter fornece ao administrador uma maneira de especificar a versão dos clientes que recebem suporte de um pool. O filtro de versão do cliente verifica a versão do cliente e pode impedir o cliente de fazer logon ou apresentar ao usuário uma mensagem que indica que ele está usando um cliente sem suporte. O filtro de versão do cliente também pode ser configurado para exibir uma mensagem para o usuário que contém a URL da versão mais recente para download do cliente.

  - O TranslationService converte um número que um usuário disca para um número E. 164 de acordo com as regras de normalização definidas pelo administrador. Para obter detalhes, consulte [regras de tradução no Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation impõe a validação de Federação em nível de locatário para mensagens de entrada e entre locatários de implantações externas.

  - Userservices é o componente de registrador de SIP, presença e conferência de um servidor front-end. Ele fornece recursos de chat, presença e conferência intimamente integrados, criados no topo do proxy SIP.

  - InterClusterRouting é responsável por direcionar chamadas para o pool de registradores primários do chamador. Para obter detalhes, consulte [componentes de VoIP do servidor front-end para o Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - O IIMFilter (filtro de IM inteligente) bloqueia as mensagens que contêm URLs clicáveis ou que tentam iniciar transferências de arquivo. O IIMFilter também verifica a versão do cliente em nome do servidor. IIMFilter afeta as transferências de arquivo iniciadas usando o Lync Server ou o Communicator. Por padrão, os links clicáveis são desativados adicionando-se um caractere de sublinhado antes do primeiro caractere do link. Um administrador pode alterar esse comportamento para que o link seja bloqueado, e, nesse caso, as mensagens que contêm URLs clicáveis ou que tentam iniciar uma transferência de arquivo são bloqueadas pelo servidor para atingir seus destinos pretendidos. O IIMFilter é instalado em todos os servidores que executam o Lync Server, exceto servidores proxy e servidores de arquivamento.

  - UserPinService é usado para verificar os números de identificação pessoal do usuário (PINs) para conferência discada.

  - Defaultrouting é o aplicativo de roteamento padrão para servidores que executam o Lync Server. Ele é habilitado por padrão. O aplicativo de roteamento é instalado em todos os servidores Standard Edition e Enterprise Edition.

  - O ExumRouting roteia chamadas para o Exchange Server Unified Messaging (UM). O ExumRouting determina o servidor do Exchange UM apropriado para direcionar a chamada quando houver uma nova mensagem de caixa postal para o depósito. O ExumRouting também manipula alguns outros aspectos de integração do Exchange UM, incluindo o roteamento para o atendedor automático e o acesso ao Assinante.

  - OutboundRouting determina o gateway que roteia uma chamada para um número de telefone de acordo com o número discado e a autorização de discagem do usuário. O OutboundRouting também manipula o redirecionamento de chamadas se um gateway não puder processar uma chamada.

  - QoEAgent recebe relatórios de dados de qualidade da experiência (QoE) de pontos de extremidade por meio de solicitações de serviço SIP e envia os dados para a fila de destino no servidor de monitoramento ou para consumidores de terceiros usando HTTP POST. Para obter detalhes, consulte Implantando o [monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation impõe a validação de Federação em nível de locatário para mensagens indo para uma implantação externa direcionada.

  - Os proxies AcpRouting INVITEem solicitações destinadas para o provedor de serviços de audioconferência ao gateway do provedor de serviços de audioconferência.

Os scripts executados em servidores de borda incluem o seguinte:

  - IIMFilter

  - OptionsHandler responderá às solicitações de entrada com o **200 OK** se a solicitação for destinada para o servidor atual. Isso é usado para a validação de topologia.

<div>

## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar um aplicativo de servidor Microsoft SIP Processing Language (MSPL) no Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico no Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

