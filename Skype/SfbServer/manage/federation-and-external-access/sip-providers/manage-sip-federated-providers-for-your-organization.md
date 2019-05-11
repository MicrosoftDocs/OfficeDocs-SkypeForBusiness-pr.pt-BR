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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como configurar o suporte de provedores federados de usuários do SIP.
ms.openlocfilehash: 64b5dcd657b72f03b25fe6de2ff6c0cda21b676d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903163"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gerenciar provedores federados SIP para sua organização no Skype para Business Server

Para configurar o suporte de provedores federados de usuários do SIP, você precisa fazer o seguinte:

  - Configurar uma ou mais políticas de acesso de usuário externo para suportar a comunicação com contatos de provedor federados SIP

  - Especifique quais provedores hospedados você deseja suportar

  - Especifique quais provedores públicos de IM você deseja suportar

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores federados SIP no Skype para Business Server

Conectividade pública de instantâneas (IM) de mensagens permite aos usuários em sua organização usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores públicos.

Skype para Business Server tem as configurações do provedor público de mensagens instantâneas. Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas na sua lista de contatos que usam esse provedor**.

Como uma configuração padrão, nenhuma dos provedores públicos são habilitadas. Você deve concluir o contrato de licença e provisionamento de trabalho antes de habilitar os provedores públicos. É possível habilitar o provedor antes de concluir o licenciamento e trabalho de provisionamento. Os usuários não poderão se comunicar com contatos nesses provedores até que o trabalho de pré-requisito seja concluído. Para obter detalhes sobre o licenciamento e provisionamento de provedores públicos, consulte [Configure políticas para controlar o acesso de usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md).

Use o procedimento a seguir para criar ou editar provedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para criar ou editar provedores públicos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **federação e acesso externo**e clique em **Provedores federados SIP**.

4.  Se você precisar criar um novo provedor público, clique em **novo** e clique em **provedor público**.

5.  Se for necessário editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e clique em **Mostrar detalhes**.

6.  Na página **Editar provedor federado SIP** , você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   selecionar esta configuração permite mensagens Instantâneas com usuários desse provedor.
    
      - **Nome do provedor:**   uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de provedores federados SIP.
    
      - **(FQDN) do serviço de borda de acesso:**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando. Essas informações são fornecidas como um item padrão e devem ser alteradas somente se o provedor público fizer uma alteração para o FQDN do serviço do provedor público de borda de acesso.
    
      - **Nível de verificação padrão:**   a configuração padrão, **Permitir que os usuários se comuniquem com pessoas na sua lista de contatos que usam esse provedor** limitará a comunicação com contatos que você tiverem aceitado e está em sua lista de contatos.
        
        A seleção de **Permitir que os usuários se comuniquem com todos usando esse provedor** remove a restrição de que você deve ter recebido e aceitou convidar um contato. Essa configuração não limitar quem pode contatá-lo da rede do provedor público.

7.  Quando você estiver definindo as configurações, clique em **Confirmar** para salvar ou clique em **Cancelar** para descartar suas alterações.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores de federados SIP hospedados no Skype para Business Server

Hospedado provedor (IM) conectividade permite que os usuários em sua organização para usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores hospedados de mensagens instantânea.

Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas na sua lista de contatos que usam esse provedor**.

Use o procedimento a seguir para criar ou editar os provedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para criar ou editar provedores hospedados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **federação e acesso externo**e clique em **Provedores federados SIP**.

4.  Se você precisar criar um novo provedor hospedado, clique em **novo** e clique em **provedor hospedado**.

5.  Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar**e clique em **Mostrar detalhes**.

6.  Na página **Editar provedor federado SIP** , você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   selecionar esta configuração habilita as comunicações com usuários desse provedor.
    
      - **Nome do provedor:**   uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de provedores federados SIP.
    
      - **(FQDN) do serviço de borda de acesso:**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando. Essas informações devem ser fornecidas pelo provedor hospedado e só deverá ser alteradas se o provedor hospedado fizer uma alteração para o FQDN do serviço do provedor hospedado de borda de acesso.
    
      - **Nível de verificação padrão:**   a configuração padrão, **Permitir que os usuários se comuniquem com pessoas na sua lista de contatos que usam esse provedor** limitará a comunicação com contatos que você tiverem aceitado e está em sua lista de contatos.
        
        A seleção de **Permitir que os usuários se comuniquem com todos usando esse provedor** remove a restrição de que você deve ter recebido e aceitou convidar um contato. Essa configuração não limitar quem pode contatá-lo da rede do provedor hospedado.

7.  Quando você estiver definindo as configurações, clique em **Confirmar** para salvar ou clique em **Cancelar** para descartar suas alterações.


## <a name="see-also"></a>Confira também


[Configurar políticas para controlar o acesso de usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

