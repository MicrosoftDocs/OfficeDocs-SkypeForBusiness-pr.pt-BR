---
title: Gerenciar fornecedores SIP federados para sua organização
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: Saiba como configurar o suporte para os usuários de provedores federados SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818362"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gerenciar provedores federados SIP para sua organização no Skype for Business Server

Para configurar o suporte para os usuários de provedores federados SIP, você precisa fazer o seguinte:

  - Configurar uma ou mais políticas de acesso de usuários externos para dar suporte à comunicação com contatos do provedor federado SIP

  - Especificar a quais provedores hospedados você deseja dar suporte

  - Especificar a quais provedores públicos de IM você deseja dar suporte

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores federados SIP públicos no Skype for Business Server

A conectividade de mensagens de chat (IM) públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores públicos.

O Skype for Business Server tem configurações de provedor público para mensagens instantâneas. Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.

Como uma configuração padrão, nenhum dos provedores públicos está habilitado. Você deve concluir o contrato de licença e o provisionamento do trabalho antes de habilitar os provedores públicos. Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento. Os usuários não poderão se comunicar com os contatos desses provedores até que o trabalho pré-requisito seja concluído. Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configurar políticas para controlar o acesso ao usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md).

Use o procedimento a seguir para criar ou editar provedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para criar ou editar provedores públicos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.

4.  Se você precisar criar um novo provedor público, clique em **novo** e, em seguida, clique em **provedor público**.

5.  Se precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

6.  Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   selecionar essa configuração habilita mensagens instantâneas com os usuários do provedor.
    
      - **Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.
    
      - **Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando. Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.
    
      - **Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.
        
        Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato. Esta configuração não limita quem pode contatá-lo na rede do provedor público.

7.  Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores federados SIP hospedados no Skype for Business Server

A conectividade de mensagens instantâneas do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores hospedados.

Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.

Use o procedimento a seguir para criar ou editar provedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para criar ou editar provedores hospedados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.

4.  Se você precisar criar um novo provedor hospedado, clique em **novo** e em **provedor hospedado**.

5.  Se você precisar editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

6.  Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   selecionar essa configuração permite a comunicação com os usuários do provedor.
    
      - **Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.
    
      - **Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando. Essas informações devem ser fornecidas pelo provedor de hospedagem e só devem ser alteradas se o provedor hospedado fizer uma alteração no FQDN do serviço de borda de acesso no provedor hospedado.
    
      - **Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.
        
        Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato. Essa configuração não limita quem pode contatá-lo na rede do provedor hospedado.

7.  Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.


## <a name="see-also"></a>Confira também


[Configurar políticas para controlar o acesso ao usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

