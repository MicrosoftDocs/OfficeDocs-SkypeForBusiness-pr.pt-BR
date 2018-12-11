---
title: 'Lync Server 2013: Gerenciando federação e acesso externo à Skype para Business Server'
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Habilitar e configurar o acesso de usuário externo ao controle se usuários externos com suporte podem colaborar com Skype interna para usuários corporativos Server.
ms.openlocfilehash: bc96f0d221071393b6c9ef7b7279159fdaa4468f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223119"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gerenciando federação e acesso externo à Skype para Business Server

Implantar um servidor de borda ou pool de borda é a primeira etapa ao suporte a usuários externos. Para obter detalhes sobre como implantar servidores de borda, consulte [Implantar o servidor de borda no Skype para Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Após instalar e configurar sua implantação interna do Skype para Business Server, os usuários internos da sua organização podem colaborar com outros usuários internos que possuem contas SIP em seu Active Directory Domain Services (AD DS). Colaboração pode incluir enviando e recebendo mensagens instantâneas e atualização de status de presença e participando de conferências (também conhecido como "reuniões"). Habilitar e configurar o acesso de usuário externo ao controle se usuários externos com suporte podem colaborar com Skype interna para usuários corporativos Server. Os usuários externos podem incluir usuários remotos da sua implantação, os usuários federados (incluindo a usuários com suporte do público de provedores de serviços (IM) de mensagens instantâneas) e participantes anônimos em conferências.

Se sua implantação incluído a instalação de um Skype para o servidor de borda do Business Server ou um pool de borda, o escopo dos tipos de comunicação possíveis é enormemente ampliado com um número de opções para acesso de usuário externo, a comunicação com os membros da outro federados SIP provedores federados de SIP e domínios. Após configurar o servidor de borda ou pool de borda, você deve habilitar os tipos de acesso de usuário externo que você deseja fornecer e configurar as políticas para controlar o acesso externo. Skype para Business Server, habilitar e configurar o acesso de usuário externo e políticas usando o Skype para painel de controle do Business Server, o [Skype do Shell de gerenciamento do servidor de negócios](../management-shell.md), ou ambas, com base nos requisitos de tarefa. 



> [!IMPORTANT]  
> Ao criar sua configuração e políticas de acesso de usuário externo, você deve compreender a precedência das políticas e como as políticas são aplicadas. Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.


Por padrão, nenhuma política estiver configurado para suportar o acesso de usuário externo, incluindo o acesso de usuário remoto, federados acesso de usuário, mesmo se você já tiver ativado o suporte ao acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de suporte para cada política de acesso de usuário externo. Isso inclui as seguintes políticas de acesso externo:

  - **Política global**   a política global é criada quando você implanta os servidores de borda. Por padrão, não há opções de acesso de usuário externo estão habilitadas na política global. Para suportar o acesso de usuário externo no nível global, você deve configurar a política global para oferecer suporte a um ou mais tipos de opções de acesso de usuário externo. A política global se aplica a todos os usuários em sua organização, mas as políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, você não removê-lo. Em vez disso, redefini-lo para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suportam para acesso de usuário externo a sites específicos. A configuração da política de site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, você pode especificar uma política de site que desabilita o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política de site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suportam para acesso de usuário remoto a usuários específicos. A configuração na política de site e substituições de diretiva de usuário global, mas somente para os usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e política de site, você pode especificar uma política de usuário que desabilita o acesso de usuário remoto e, em seguida, atribuir essa política de usuário para usuários específicos. Se você criar uma política de usuário, você deverá aplicá-la a um ou mais usuários antes que ele entra em vigor.

Para determinar quais configurações e quais políticas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Você deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagens instantâneas, conferência Web e áudio/vídeo?**

Defina as configurações conforme detalhado nos tópicos [Configure políticas para controlar o acesso de usuário remoto](external-access-policies/configure-policies-to-control-remote-user-access.md)e [Habilitar ou desabilitar a federação e conectividade IM pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Você deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas por usuários em sua implantação?**

Defina as configurações conforme detalhado no tópico [Atribuir políticas de conferência para oferecer suporte a usuários anônimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [criar políticas de conferência](../conferencing/create-policies.md).

**Você deseja permitir que os usuários se comuniquem com contatos do domínio federado SIP?**

Defina as configurações conforme detalhado nos tópicos [Configure políticas para controlar federados acesso de usuário](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitar ou desabilitar a federação e conectividade IM pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Gerenciar SIP federated domínios para sua organização](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Se você habilitou a comunicação com domínios federados SIP, você deseja habilitar a descoberta automática federação SIP?**

Defina as configurações conforme detalhado no tópico [Habilitar ou desabilitar a descoberta de parceiros de Federação](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Se você habilitou a comunicação com domínios federados SIP, você deseja habilitar o envio de um aviso de isenção para contatos federados notificando que você use o arquivamento e que as comunicações poderão ser arquivadas?**

Defina as configurações conforme detalhado no tópico [Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que permitem a comunicação com provedores públicos?**

Configure as configurações conforme detalhadas nos tópicos [Configure políticas para o controle de usuário público acessar](external-access-policies/configure-policies-to-control-public-user-access.md), [Habilitar ou desabilitar a federação e conectividade IM pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Create or edit public SIP provedores federados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que estão executando o Microsoft Office 365 e Skype para Business Online de provedores hospedados?**

Defina as configurações conforme detalhado nos tópicos a [Habilitar ou desabilitar a federação e conectividade IM pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [Create or edit hosted SIP provedores federados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Sua implantação está configurada em um domínio dividido (também conhecido como um híbrido), onde alguns usuários têm sua servidor primário em uma implantação no local e outros usuários são configurados com um servidor primário em um ambiente online?**

Configure as configurações conforme detalhadas nos tópicos [Configure políticas para controlar o acesso de usuário federado](external-access-policies/configure-policies-to-control-federated-user-access.md), [Habilitar ou desabilitar a federação e conectividade IM pública](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Create or edit hosted SIP provedores federados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Você pode configurar as configurações de acesso de usuário externo, incluindo todas as diretivas que você deseja usar para controlar o acesso de usuário externo, mesmo se você não tiver ativado o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações que você configurar estão em vigor somente quando você tiver acesso de usuário externo habilitado para sua organização. Usuários externos não podem se comunicar com usuários de sua organização, quando o acesso de usuário externo está desativado ou se nenhuma política de acesso de usuário externo estiverem configurada para oferecer suporte a ele.

Sua implantação de borda autentica os tipos de usuários externos (exceto para os usuários anônimos, que são autenticados pela ID de conferência e uma chave de acesso que será enviada para o participante anônimo quando você cria os participantes da conferência e convidar) e controles com base em como você configura o suporte de borda de acesso. Para controlar as comunicações, você pode configurar uma ou mais políticas e definir as configurações que definem como os usuários dentro e fora da sua implantação se comunicar entre si. As políticas e configurações incluem a política global de padrão para o acesso de usuário externo, além das políticas de site e de usuário que você pode criar e configurar para permitir que um ou mais tipos de acesso de usuário externo para sites ou usuários específicos.

