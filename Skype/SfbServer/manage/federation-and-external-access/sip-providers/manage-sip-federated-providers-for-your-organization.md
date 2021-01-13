---
title: Gerenciar fornecedores SIP federados para sua organização
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como configurar o suporte para usuários de provedores federados SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823561"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gerenciar provedores SIP federados para sua organização no Skype for Business Server

Para configurar o suporte de usuários de provedores SIP federados, você precisará fazer o seguinte:

  - Configurar uma ou mais políticas de acesso do usuário externo se comunicando com contatos do provedor federado SIP

  - Especifique quais provedores hospedados você deseja suportar.

  - Especifique quais provedores públicos de IM você deseja suportar

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores sip públicos federados no Skype for Business Server

A conectividade pública de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores públicos.

O Skype for Business Server tem configurações de provedor público para mensagens instantâneas. Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão permite que os usuários se comuniquem somente com pessoas em sua lista de Contatos que usam esse **provedor.**

Como configuração padrão, nenhum dos provedores públicos está habilitado. Você deve concluir o contrato de licença e o trabalho de provisionamento antes de habilitá-los. Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento. Os usuários não poderão se comunicar com contatos nesses provedores até que o trabalho de pré-requisito seja concluído. Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte Configurar políticas [para controlar o acesso de usuários públicos.](../external-access-policies/configure-policies-to-control-public-user-access.md)

Use o procedimento a seguir para criar ou editar provedores públicos.


### <a name="to-create-or-edit-public-providers"></a>Para criar ou editar provedores públicos

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.

4.  Se você precisar criar um novo provedor público, clique em **Novo** e em **Provedor público.**

5.  Se você precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar** e em **Mostrar detalhes.**

6.  Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   Selecionar essa configuração habilita as IMs com os usuários desse provedor.
    
      - **Nome do provedor:**    Uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de Provedores Federados SIP.
    
      - **Serviço de Borda de Acesso (FQDN):**   Uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de Borda de Acesso do provedor que você está configurando. Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de Borda de Acesso no provedor público.
    
      - **Nível de verificação padrão:**    A configuração padrão, **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**, limitará a comunicação aos contatos que foram aceitos e estão em sua lista de contatos.
        
        Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Essa configuração não limita quem pode entrar em contato com você a partir da rede do provedor público.

7.  Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Criar ou editar provedores federados SIP hospedados no Skype for Business Server

A conectividade de mensagens instantâneas (IM) do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores hospedados.

Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**.

Use o procedimento a seguir para criar ou editar provedores hospedados.

### <a name="to-create-or-edit-hosted-providers"></a>Para criar ou editar provedores hospedados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.

4.  Se for necessário criar um novo provedor hospedado, clique em **Novo** e em **Provedor hospedado**.

5.  Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar** e em **Exibir detalhes**.

6.  Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   Selecionar esta configuração habilita as comunicações com os usuários deste provedor.
    
      - **Nome do provedor:**    Uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de Provedores Federados SIP.
    
      - **Serviço de Borda de Acesso (FQDN):**   Uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de Borda de Acesso do provedor hospedado que você está configurando. Esta informação deve ser fornecida pelo provedor hospedado, e só deve ser alterada se o provedor fizer uma mudança no FQDN do serviço de Borda de Acesso.
    
      - **Nível de verificação padrão:**    A configuração padrão, **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**, limitará a comunicação aos contatos que foram aceitos e estão em sua lista de contatos.
        
        Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Esta configuração não limita quem pode entrar em contato com você a partir da rede do provedor hospedado.

7.  Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.


## <a name="see-also"></a>Confira também


[Configurar políticas para controlar as acessos de usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

