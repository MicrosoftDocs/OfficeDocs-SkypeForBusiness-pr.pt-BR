---
title: 'Lync Server 2013: gerenciar Federação e acesso externo ao Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você habilita e configura o acesso de usuários externos para controlar se os usuários externos com suporte podem colaborar com usuários internos do Skype for Business Server.
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280100"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gerenciamento de Federação e acesso externo ao Skype for Business Server

Implantar um servidor de borda ou um pool de bordas é o primeiro passo para dar suporte a usuários externos. Para obter detalhes sobre a implantação de servidores de borda, consulte [implantar servidor de borda no Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Após a instalação e a configuração da sua implantação interna do Skype for Business Server, os usuários internos em sua organização podem colaborar com outros usuários internos que tenham contas SIP nos serviços de domínio Active Directory (AD DS). A colaboração pode incluir o envio e o recebimento de mensagens instantâneas e a atualização do status de presença e a participação em conferências (também conhecidas como "reuniões"). Você habilita e configura o acesso de usuários externos para controlar se os usuários externos com suporte podem colaborar com usuários internos do Skype for Business Server. Os usuários externos podem incluir usuários remotos da sua implantação, usuários federados (incluindo usuários com suporte de provedores de serviços de mensagens instantâneas públicas) e participantes anônimos em conferências.

Se a sua implantação incluía a instalação de um servidor de borda do Skype for Business Server ou um pool de bordas, o escopo dos possíveis tipos de comunicação será amplamente expandido com várias opções para acesso de usuário externo, comunicação com membros de outros objetos SIP federados domínios e provedores federados SIP. Depois de configurar o servidor de borda ou o pool de bordas, habilite os tipos de acesso de usuário externo que você deseja fornecer e configure as políticas para controlar o acesso externo. No Skype for Business Server, você habilita e configura o acesso externo a usuários e políticas usando o painel de controle do Skype for Business Server, o [Shell de gerenciamento do Skype for Business Server](../management-shell.md), ou ambos, com base nos requisitos da tarefa. 



> [!IMPORTANT]  
> Ao projetar sua configuração e políticas para acesso de usuário externo, você deve entender a precedência de políticas e como as políticas são aplicadas. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.


Por padrão, nenhuma política é configurada para dar suporte ao acesso externo do usuário, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política. Isso inclui as seguintes políticas de acesso externo:

  - **Política global a**   política global é criada quando você implanta seus servidores de borda. Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global. Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo. A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, não a removerá. Em vez disso, redefina-o para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos. A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos. Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.

Para determinar quais configurações de configuração e quais diretivas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Você deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagens instantâneas, conferências da Web e áudio/vídeo?**

Defina as configurações conforme detalhado nos tópicos Configurando [políticas para controlar](external-access-policies/configure-policies-to-control-remote-user-access.md)o acesso do usuário remoto e [habilitar ou desabilitar a conectividade de mensagens de chat pública e de Federação](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas pelos usuários na sua implantação?**

Defina as configurações conforme detalhado no tópico [atribuir políticas de conferência para dar suporte a usuários anônimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [criar políticas de conferência](../conferencing/create-policies.md).

**Deseja permitir que os usuários se comuniquem com os contatos do domínio federado do SIP?**

Defina as configurações conforme detalhado nos tópicos Configurando [políticas para controlar o acesso de usuários federados](external-access-policies/configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e a Federação](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [gerenciar domínios federados SIP para sua organização](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Se você tiver habilitado a comunicação com domínios federados SIP, deseja habilitar a descoberta automática de Federação SIP?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar a descoberta de parceiros de Federação](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Se você habilitou a comunicação com domínios de Federação SIP, deseja habilitar o envio de um aviso de isenção de responsabilidade a contatos federados notificando que você usa o arquivamento e que as comunicações podem ser arquivadas?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar o envio de uma isenção de arquivamento para parceiros federados no](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que permitem a comunicação com provedores públicos?**

Defina as configurações conforme detalhado nos tópicos [Configurar políticas para controlar o acesso ao usuário público](external-access-policies/configure-policies-to-control-public-user-access.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e agrupamento](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [criar ou editar provedores federados SIP públicos](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que sejam provedores que executam o Microsoft Office 365 e o Skype for Business Online?**

Defina as configurações conforme detalhado nos tópicos [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [criar ou editar provedores federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**A implantação está configurada em um domínio dividido (também conhecido como híbrido), no qual alguns usuários têm o servidor primário em uma implantação local e outros usuários estão configurados com um servidor primário em um ambiente online?**

Defina as configurações conforme detalhado nos tópicos [Configurar políticas para controlar o acesso do usuário federado](external-access-policies/configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e agrupamento](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [criar ou editar provedores federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Você pode definir as configurações de acesso de usuário externo, incluindo as políticas que deseja usar para controlar o acesso de usuários externos, mesmo que você não tenha habilitado o acesso de usuários externos para a sua organização. No entanto, as políticas e outras configurações que você configura estão em vigor apenas quando você tem acesso de usuário externo habilitado para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso ao usuário externo estiver desabilitado ou se nenhuma política de acesso externo do usuário estiver configurada para dar suporte a ele.

Sua implantação de borda autentica os tipos de usuários externos (exceto para usuários anônimos, que são autenticados pela ID de conferência e uma chave de usuário que é enviada para o participante anônimo quando você cria os participantes da conferência e convida) e os controles acesso com base em como você configura o suporte de borda. Para controlar a comunicação, você pode configurar uma ou mais políticas e definir configurações que definem como os usuários dentro e fora da sua implantação se comunicam uns com os outros. As políticas e configurações incluem a política global padrão para acesso ao usuário externo, além das políticas de site e de usuário que você pode criar e configurar para habilitar um ou mais tipos de acesso de usuários externos para sites ou usuários específicos.

