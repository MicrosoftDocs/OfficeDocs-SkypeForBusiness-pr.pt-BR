---
title: Gerenciar domínios SIP federados para sua organização
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como gerenciar e configurar domínios SIP com os quais você pode federar,
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818232"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gerenciar domínios federados SIP para sua organização no Skype for Business Server


Para gerenciar e configurar domínios SIP com os quais você pode federar, você pode fazer o seguinte:

  - Crie ou edite uma lista de domínios permitidos de domínios de parceiros federados SIP.

  - Criar ou editar uma lista de domínios bloqueados de domínios federados SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar o suporte para domínios externos permitidos no Skype for Business Server

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios específicos podem federar a sua organização. Você pode configurar um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que pode precisar se comunicar com mais de 1.000 de seus usuários ou talvez precise enviar mais de 20 mensagens por segundo. Se a descoberta de parceiro não estiver habilitada para sua organização, somente os usuários de domínios externos que você adicionar à lista de domínios permitidos poderão participar de mensagens instantâneas e conferência com os usuários da sua organização. Se quiser restringir o acesso de um domínio federado a um servidor específico executando o serviço de borda de acesso do parceiro federado, você pode especificar o nome de domínio do servidor que executa o serviço de borda de acesso para cada domínio na lista de domínios permitidos.

> [!NOTE]  
> Este procedimento descreve como configurar o suporte para domínios específicos, mas a implementação do suporte a usuários federados também requer que você habilite o suporte para usuários federados para sua organização e configure e aplique políticas para controlar quais usuários podem Colabore com usuários federados. Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md). Para obter detalhes sobre a configuração de políticas para controlar a Federação, consulte [Configurar políticas para controlar o acesso de usuários federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para adicionar um domínio externo à lista de domínios permitidos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **domínios federados**.
4.  Na página **domínios federados** , clique em **novo**e, em seguida, clique em **domínio permitido**.
5.  Em **novos domínios federados**, faça o seguinte:
    
      - Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.       

        > [!NOTE]  
        > Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que está executando o serviço de borda de acesso. O nome não pode exceder 256 caracteres de comprimento.<BR><br>A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente. O Skype for Business Server impede que isso aconteça para que você não precise sincronizar suas listas.
    
      - Se você quiser restringir o acesso para esse domínio federado para os usuários de um servidor específico executando o serviço de borda de acesso, no **serviço de borda de acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de borda de acesso.    
      - Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada domínio de parceiro federado que você deseja permitir.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar o suporte para domínios externos bloqueados no Skype for Business Server 

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão bloqueados a partir da Federação em sua organização. A lista de domínios bloqueados atuará como uma lista de blocos (lista de entradas explícitas que não são permitidas) e será aplicada à descoberta de domínio federado, se você tiver essa opção habilitada. Para obter detalhes, consulte [habilitar ou desabilitar a descoberta de parceiros de Federação](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquear um ou mais domínios externos para se conectar à sua organização. Para fazer isso, adicione o domínio à lista de domínios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para adicionar um domínio externo à lista de domínios bloqueados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**.
4.  Clique em **domínios federados**, clique em **novo**e, em seguida, clique em **domínio bloqueado**.
5.  Em **novos domínios federados**, faça o seguinte:
    
      - Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado que você deseja bloquear.

        > [!NOTE]  
        > O nome não pode exceder 256 caracteres de comprimento.<BR><br>A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente. O Skype for Business Server impede que isso aconteça para que você não precise sincronizar suas listas.
   
      - Adicionais Em **Comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada parceiro federado que você deseja bloquear.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Confira também

[Configurar políticas para controlar acesso de usuário federado](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar ou desabilitar descoberta de parceiros de federação](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

