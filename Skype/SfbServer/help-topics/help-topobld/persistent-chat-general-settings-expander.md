---
title: Expansor de Configurações Gerais de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Edite as configurações gerais do servidor de chat persistente ou do pool do servidor de chat persistente Configurando ou definindo essas propriedades:'
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819473"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de Configurações Gerais de Chat Persistente
 
Edite as configurações **gerais** do servidor de chat persistente ou do pool do servidor de chat persistente Configurando ou definindo essas propriedades:
  
 **Geral**
  
- **FQDN**: Edite essa configuração para definir o nome de domínio totalmente qualificado do seu servidor de chat persistente ou pool de servidor de chat persistente
    
- **Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool. Essa configuração torna mais fácil para os usuários associarem um determinado servidor de chat persistente ou pool persistente do servidor de chat com base no nome para exibição em vez de ser mais difícil compreender o nome de domínio totalmente qualificado.
    
- **Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.
    
Edite as configurações de **associações** para o servidor de chat persistente ou o pool de servidores de chat persistente Configurando ou definindo essas propriedades:
  
 **Associações**
  
- **Repositório do SQL Server**: escolha o repositório do SQL Server e a instância nomeada opcional na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja principal do SQL Server.
    
    Se você optou por habilitar o espelhamento da loja do SQL Server, selecione a loja e a instância na lista **espelhando o SQL Server Store**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja principal do SQL Server.
    
    Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **usar o backup de repositórios do SQL Server para habilitar a recuperação de desastres** se você quiser habilitar o uso da recuperação de desastre do SQL Server
    
    Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Repositório do SQL Server de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento do armazenamento de espelhamento do SQL Server de backup.
    
    Se você optou por habilitar o espelhamento de backup do SQL Server Store, selecione a loja e a instância no espelho da lista **backup do SQL Server Store**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático do repositório do SQL Server de backup.
    
    Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade
    
    Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja do SQL Server de conformidade.
    
    Se você optou por habilitar o espelhamento de compatibilidade do SQL Server Store, selecione a loja e a instância no espelho da lista **conformidade do SQL Server Store**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja do SQL Server de conformidade.
    
    Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se você quiser habilitar o espelhamento para a loja do SQL Server de conformidade.
    
    Se você optou por habilitar o espelhamento de compatibilidade do SQL Server Store, selecione a loja e a instância no espelho da lista de **conformidade de backup do SQL Server Store**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** se desejar failover automático da loja do SQL Server de conformidade de backup.
    
    Se você optou por habilitar a testemunha de espelhamento da loja do SQL Server para habilitar o failover automático, selecione a loja e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- **Repositório de arquivos** Selecione um local de armazenamento de arquivos na lista ou clique em **novo** para criar um novo repositório de arquivos.
    
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
