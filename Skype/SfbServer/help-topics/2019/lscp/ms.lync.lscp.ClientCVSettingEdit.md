---
title: Configuração de Versão do Cliente Criar Novo ou Editar Existente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que qualquer controle de versão de cliente ocorra.'
---

# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuração da Versão de Cliente: Criar Nova ou Editar Existente

As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que qualquer controle de versão de cliente ocorra.

Também é possível criar configurações de versão do cliente específicas do site, permitindo a habilitação ou desabilitação do controle de versão do cliente por site. A configuração específica do site tem precedência sobre a configuração Global.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar ou modificar o nome da configuração de versão do cliente.

- Habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site específico.

- Adicionar ou modificar a ação padrão da configuração de versão do cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Escopo** Identifica o escopo (Global ou Site) da configuração da versão do cliente.

- **Nome** Você pode adicionar ou modificar o nome da configuração da versão do cliente.

- **Habilitar o controle de versão** Você pode habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site, dependendo do escopo da configuração.

- **Ação padrão** Você pode selecionar a ação padrão que será aplicada quando um usuário tentar fazer logoff usando um aplicativo cliente para o qual não há política de versão do cliente específica. Você tem as seguintes opções:

  - **Permitir** Permite que o cliente faça logoff se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente.

  - **Bloquear** Impede que o cliente faça logon se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente.

  - **Bloquear com URL** Impede que o cliente faça logon se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL em que um cliente mais recente pode ser baixado.

  - **Permitir com URL** Permite que o cliente faça logoff se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.

  - **URL** Se você **selecionou Bloquear com URL** ou **Permitir com URL**, você pode especificar a URL de download do cliente para incluir na mensagem de erro.

Para obter detalhes sobre interoperabilidade entre clientes e versões do cliente, consulte [Interoperabilidade do](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) cliente na documentação planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) na documentação Operações.