---
title: 'Lync Server 2013: Configurando suporte para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 143e7e661f793f7a05cb2fdbad8cdab8acaf660e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configurando suporte para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Implantar um servidor de borda ou um pool de bordas é o primeiro passo para dar suporte a usuários externos. Para obter detalhes sobre a implantação de servidores de borda, consulte [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Uma consideração importante para a configuração das políticas é entender a precedência de políticas e como as políticas são aplicadas. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

Depois de concluir a configuração de um servidor de borda ou de um pool de bordas, você deve habilitar os tipos de acesso de usuário externo que deseja fornecer e definir as configurações para o acesso externo. No Lync Server 2013, habilite e configure o acesso de usuários externos e políticas usando o painel de controle do Lync Server, o Shell de gerenciamento do Lync Server ou ambos, de acordo com os requisitos da tarefa.

Para dar suporte ao acesso de usuário externo, você deve fazer o seguinte:

  - **Habilite o suporte para sua organização**   para habilitar o suporte ao acesso de usuários externos na sua implantação, você deve habilitar cada tipo de acesso externo ao qual deseja dar suporte. Habilite e desabilite o suporte ao acesso de usuários externos editando as configurações globais ou criando e configurando uma política de site ou de usuário na página de **política de acesso externo** no grupo **agrupamento e acesso externo** do painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e cmdlets associados. Cmdlets para gerenciar a **política de acesso externo** são encontrados nos [cmdlets agrupamento de agrupamento e acesso externo no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Habilitar o suporte para acesso externo especifica que os servidores que executam o serviço de borda de acesso do Lync Server ofereçam suporte à comunicação com usuários e servidores externos. Os usuários internos e externos não podem se comunicar enquanto o acesso de usuário externo estiver desabilitado ou se as políticas ainda não tiverem sido configuradas para dar suporte a ele.

  - **Configurar e atribuir uma ou mais políticas**   para dar suporte a acesso externo a usuários, você configura políticas para atender a requisitos que incluem:
    
      - **Políticas de acesso externo**   criadas com um escopo de site ou de usuário (uma política global existe por padrão e não tem configurações habilitadas). Você cria e configura políticas para controlar o uso de um ou mais tipos de acesso de usuário externo, incluindo o acesso de usuário federado (incluindo, se selecionado, domínios de XMPP federados) usuários remotos acesso de usuário e provedores públicos de serviços de mensagens de chat com suporte. Você configura políticas externas no painel de controle do Lync Server usando a política global ou uma ou mais políticas de site e de usuário criadas administrativamente, na página **política de acesso externo** no grupo **Federação e acesso externo** . A política global não pode ser excluída. Você cria e configura qualquer política de site e de usuário que você deseja usar para limitar o acesso de usuários externos a sites ou usuários específicos. Políticas globais e de site são automaticamente atribuídas. Se você criar e configurar uma política de usuário, deverá atribuí-la a usuários específicos usando a página configuração do usuário no painel de controle do Lync Server na página **usuários** . Localize o usuário ou os usuários aos quais você deseja que essa política se aplique e atribua a política. a quem você deseja que ele seja aplicado. Para atribuir uma política de usuário configurada a um usuário, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Cada política de acesso externo do usuário pode dar suporte a um ou mais dos seguintes: acesso de usuário remoto, acesso de usuário federado SIP, acesso de usuário federado XMPP e conectividade de IM pública.
    
      - **Políticas de conferência**   você cria e configura políticas para controlar a conferência em sua organização, incluindo quais usuários em sua organização podem convidar usuários anônimos para conferências que eles hospedam. Na página **conferência** do painel de controle do Lync Server são configurações de política no escopo global, de site e de usuário que controlam as configurações de controle para as conferências reais. Para obter detalhes, consulte [Gerenciando reuniões e conferências no Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Você habilita usuários anônimos para conferências, usuários remotos e usuários federados na página de **configuração de borda de acesso** . A política na **configuração de borda de acesso** é global no escopo. Não há opções para definir uma política de site ou de usuário. O escopo é controlado na página de **política de acesso externo** por meio do uso de configurações de política global, de site ou de usuário.
        
        Por exemplo, se você quiser permitir que os usuários criem, convidem e gerenciem conferências com usuários remotos, você deve definir **habilitar comunicações com usuários remotos** na política de **acesso externo** global, site ou política de usuário e **habilitar comunicações com usuários remotos** na página **configuração de borda de acesso** . Da mesma forma, para permitir a conferência com usuários anônimos ou parceiros federados com os quais você tem uma relação definida (como provedores e provedores de SIP federados configurados – a Federação do XMPP não oferece suporte à conferência), você define **habilitar comunicações com usuários públicos** e **habilitar comunicações com usuários federados** na política de **acesso externo** , site ou política de usuário. Em seguida, selecione configurações de política global complementar **para habilitar o acesso de usuários anônimos** e **habilitar a conectividade de mensagens instantâneas federadas e federada** na página **configuração de borda de acesso** .

Você pode definir as configurações de acesso de usuário externo, incluindo as políticas que deseja usar para controlar o acesso de usuários externos, mesmo que você não tenha habilitado o acesso de usuários externos para a sua organização. No entanto, as políticas e outras configurações que você configura estão em vigor apenas quando você tem acesso de usuário externo habilitado para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso ao usuário externo estiver desabilitado ou se nenhuma política de acesso externo do usuário estiver configurada para dar suporte a ele.

Sua implantação de borda autentica os tipos de usuários externos (exceto para usuários anônimos, que são autenticados pela ID de conferência e uma chave de usuário que é enviada para o participante anônimo quando você cria os participantes da conferência e convida) e os controles acesso com base em como você configura o suporte de borda. Para controlar a comunicação, você pode configurar uma ou mais políticas e definir configurações que definem como os usuários dentro e fora da sua implantação se comunicam uns com os outros. As políticas e configurações incluem a política global padrão para acesso ao usuário externo, além das políticas de site e de usuário que você pode criar e configurar para habilitar um ou mais tipos de acesso de usuários externos para sites ou usuários específicos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Habilitar ou desabilitar acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar ou desabilitar acesso de usuário anônimo no Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Atribuir políticas de conferência para suporte de usuários anônimos no Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

