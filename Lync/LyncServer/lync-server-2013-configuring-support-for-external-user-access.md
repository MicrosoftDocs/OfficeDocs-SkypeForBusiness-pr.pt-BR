---
title: 'Lync Server 2013: Configurando o suporte para acesso de usuário externo'
description: 'Lync Server 2013: Configurando o suporte para acesso de usuário externo.'
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
ms.openlocfilehash: d5a91f9b285a80ff6a0f3c58c2c12f88d72aac98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556887"
---
# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configurando suporte para acesso de usuário externo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Implantar um Servidor de borda ou um pool de Borda é a primeira etapa para suportar usuários externos. Para obter detalhes sobre como implantar servidores de borda, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Uma consideração importante sobre a configuração de políticas é entender a precedência das políticas e como elas são aplicadas. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

Após concluir a configuração de um Servidor de borda ou pool de Borda, você deve habilitar os tipos de acesso de usuário externo que deseja suportar e configurar o suporte para acesso externo. No Lync Server 2013, você habilita e configura o acesso de usuário externo e políticas usando o painel de controle do Lync Server, o Shell de gerenciamento do Lync Server ou ambos, com base nos requisitos de tarefa.

Para suportar o acesso de usuário externo, você deve fazer o seguinte:

  - **Habilitar o suporte para sua organização**     Para habilitar o suporte para acesso de usuário externo em sua implantação, habilite cada tipo de acesso externo que você deseja suportar. Habilite e desabilite o suporte para acesso de usuário externo editando as configurações globais ou criando e configurando uma política de site ou de usuário na página **política de acesso externo** no grupo **Federação e acesso externo** do painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e cmdlets associados. Os cmdlets para gerenciar a **política de acesso externo** são encontrados no tópico [Federação e cmdlets de acesso externo no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Habilitar o suporte para acesso externo especifica que os servidores que executam o serviço de borda de acesso do Lync Server dão suporte a comunicações com usuários e servidores externos. Os usuários internos e externos não podem se comunicar enquanto o acesso de usuário externo está desabilitado ou as políticas ainda não foram configuradas para oferecer suporte a ele.

  - **Configurar e atribuir uma ou mais políticas**     Para dar suporte ao acesso de usuário externo, configure as políticas para atender aos requisitos que incluem:
    
      - Políticas de acesso **externo**     Criado com um escopo de site ou de usuário (uma política global existe por padrão e não tem configurações habilitadas). Você cria e configura políticas para controlar o uso de um ou mais tipos de acesso de usuário externo, incluindo o acesso de usuário federado (incluindo, se selecionados, domínios XMPP federados) usuários remotos acesso de usuário e provedores de serviço de mensagens instantâneas públicos compatíveis. Configure as políticas externas no painel de controle do Lync Server usando a política global ou uma ou mais políticas de site e de usuário criadas de forma administrativa, na página **política de acesso externo** no grupo **Federação e acesso externo** . A política global não pode ser excluída. Você cria e configura qualquer política de site e de usuário que você deseja usar para limitar o acesso de usuário externo para sites ou usuários específicos. As políticas globais e de site são atribuídas automaticamente. Se você criar e configurar uma política de usuário, deverá atribuí-la aos usuários específicos usando a página configuração do usuário no painel de controle do Lync Server na página **usuários** . Localize os usuários aos quais você deseja aplicar essa política e atribua a política. para quem você deseja aplicar. Para atribuir uma política de usuário configurada a um usuário, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Cada política de acesso de usuário externo pode dar suporte a uma ou mais das seguintes opções: acesso de usuário remoto, acesso de usuário federado SIP, acesso de usuário federado XMPP e conectividade de IM pública.
    
      - **Políticas**     de conferência Você cria e configura políticas para controlar a conferência em sua organização, incluindo quais usuários em sua organização podem convidar usuários anônimos para conferências que eles hospedam. Na página **conferência** do painel de controle do Lync Server estão as configurações de política no escopo global, de site e de usuário que controlam as configurações de controle das conferências reais. Para obter detalhes, consulte [Managing reuniões e conferências no Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Você habilita usuários anônimos, usuários remotos e federados para conferências na página **Configuração da borda de acesso**. A política na **Configuração de borda de acesso** é global em escopo. Não há opções para definir uma política de local ou de usuário. O escopo é controlado na página **Política de acesso externo** por meio da utilização de configurações de políticas globais, de local ou do usuário.
        
        Por exemplo, se você quiser permitir aos usuários criar, convidar e gerenciar conferências com usuários remotos, você deve definir **Habilitar comunicações com usuários remotos** na **Política de acesso externo** global, de local ou do usuário, e **Habilitar comunicações com usuários remotos** na página **Configuração de borda de acesso**. De forma semelhante, para permitir conferências com usuários anônimos ou parceiros federados com os quais você tem um relacionamento definido (como domínios e parceiros SIP federados configurados – a federação XMPP não suporta conferências), você deve definir **Habilitar comunicações com usuários públicos** e **Habilitar comunicações com usuários federados** na **Política de acesso externo** global, de site ou do usuário. Após, você deve selecionar as configurações complementares de política global **Habilitar acesso de usuário anônimo a conferências** e **Habilitar conectividade de IM pública e federada** na página **Configuração da borda de acesso**.

É possível definir configurações de acesso de usuário externo, incluindo qualquer política que deseja usar para controlar o acesso de usuário externo, mesmo se não habilitou o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações definidas entram em vigor apenas quando você habilitou acesso de usuário externo para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso de usuário externo está desabilitado ou se nenhuma política de acesso do usuário externo está configurada para suporá-lo.

Sua implantação de borda autentica os tipos de usuário externos (exceto usuários anônimos que são autenticados pelo ID da conferência e uma chave de passe enviada ao participante anônimo ao criar a conferência e convidar os participantes) e controla o acesso com base em como você configura seu suporte de borda. Para poder controlar as comunicações, é possível configurar uma ou mais políticas e definir outras configurações que definem como os usuários dentro e fora da sua implantação se comunicam entre si. As políticas e configurações incluem a política global padrão para acesso de usuário externo, além de políticas local e do usuário que podem ser criadas e configuradas para habilitar um ou mais tipos de acesso de usuário externo para locais ou usuários específicos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Habilitar ou desabilitar o acesso de usuário anônimo no Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

