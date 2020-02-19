---
title: Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb195ee5826cbb63f7fc718a038761f10199135
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-09-26_

Um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) é um aplicativo somente de script que usa uma linguagem de script em vez da API do Microsoft Lync 2010. O MSPL fornece controle mais granular sobre os comportamentos de filtragem e proxy, além de um recurso para despachar mensagens específicas para aplicativos SIP baseados em transações. O MSPL é usado especificamente para filtrar e rotear mensagens SIP. Os aplicativos do MSPL são executados no mesmo processo que o módulo userservices, enquanto um programa baseado na API do Lync 2010 é executado em um processo separado.

Você pode usar a página **aplicativo de servidor** no grupo **topologia** do painel de controle do Lync Server para ver uma lista de aplicativos de servidor do MSPL que são executados em servidores front-end no seu ambiente do Lync Server 2013. A lista mostra os scripts disponíveis para cada pool, bem como se eles estão habilitados ou críticos. Os scripts são executados na ordem em que são listados.

Eles incluem:

  - O ClientVersionFilter fornece ao administrador uma maneira de especificar a versão de clientes com suporte em um pool. O filtro de versão do cliente verifica a versão do cliente e pode impedir que o cliente faça logon ou apresente o usuário com uma mensagem que indica que ele está usando um cliente que não tem suporte. O filtro de versão do cliente também pode ser configurado para exibir uma mensagem para o usuário que contém a URL da versão mais recente para download do cliente.

  - TranslationService converte um número que um usuário disca para um número E. 164 de acordo com as regras de normalização definidas pelo administrador. Para obter detalhes, consulte [regras de conversão no Lync Server 2013](lync-server-2013-translation-rules.md).

  - O IncomingFederation impõe a validação de Federação no nível do locatário para mensagens de entrada e de inter-locatário de implantações externas.

  - Userservices é o componente de registrador SIP, presença e conferência de um servidor front-end. Ele oferece recursos de IM, presença e conferência intimamente integrados, criados na parte superior do proxy SIP.

  - InterClusterRouting é responsável por rotear chamadas para o pool de registradores primários do chamador. Para obter detalhes, consulte [componentes de VoIP do servidor front-end para Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (filtro de IM inteligente) bloqueia mensagens que contêm URLs que podem ser clicadas ou que tentam iniciar transferências de arquivo. O IIMFilter também verifica a versão do cliente em nome do servidor. IIMFilter afeta transferências de arquivos que são iniciadas usando o Lync Server ou o Communicator. Por padrão, os links que podem ser clicados são desabilitados adicionando um caractere de sublinhado antes do primeiro caractere do link. Um administrador pode alterar esse comportamento para que o link seja bloqueado, caso em que as mensagens que contenham URLs de clique ou que tentam iniciar uma transferência de arquivo sejam bloqueadas pelo servidor para atingir seus destinos pretendidos. O IIMFilter está instalado em todos os servidores que executam o Lync Server, exceto servidores proxy e servidores de arquivamento.

  - UserPinService é usado para verificar números de identificação pessoal do usuário (PINs) para conferência discada.

  - Defaultrouting é o aplicativo de roteamento padrão para servidores que executam o Lync Server. Ele é habilitado por padrão. O aplicativo de roteamento é instalado em todos os servidores Standard Edition e Enterprise Edition.

  - ExumRouting roteia chamadas para a UM (Unificação de mensagens) do Exchange Server. ExumRouting determina o servidor de UM do Exchange apropriado para direcionar a chamada quando houver uma nova mensagem de caixa postal para o depósito. O ExumRouting também lida com outros aspectos de integração do UM do Exchange, incluindo o roteamento para o atendedor automático e o acesso ao Assinante.

  - OutboundRouting determina o gateway que roteia uma chamada para um número de telefone de acordo com o número discado e a autorização de discagem do usuário. OutboundRouting também gerencia o redirecionamento de chamadas se um gateway não puder processar uma chamada.

  - O QoEAgent recebe relatórios de dados de QoE (qualidade da experiência) de pontos de extremidade por meio de solicitações de serviço SIP e envia os dados para a fila de destino no servidor de monitoramento ou para consumidores de terceiros usando HTTP POST. Para obter detalhes, consulte [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - O OutgoingFederation impõe a validação de Federação em nível de locatário para mensagens indo para uma implantação externa de destino.

  - Os proxies do AcpRouting CONVIDEm solicitações destinadas ao provedor de audioconferência para o gateway de provedor de audioconferência.

Os scripts executados em servidores de borda incluem o seguinte:

  - IIMFilter

  - OptionsHandler responderá às solicitações de opções de entrada com **200 OK** se a solicitação for destinada ao servidor atual. Isso é usado para validação de topologia.

<div>

## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

