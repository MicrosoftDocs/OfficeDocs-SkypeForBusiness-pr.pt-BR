---
title: Expansor de Configurações Gerais de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Edite as configurações Gerais para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente configurando ou definindo estas propriedades:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823844"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de Configurações Gerais de Chat Persistente
 
Edite as **configurações** Gerais para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo ou definindo estas propriedades:
  
 **Geral**
  
- **FQDN:** Edite essa configuração para definir o nome de domínio totalmente qualificado do seu Servidor de Chat Persistente ou pool de Servidor de Chat Persistente
    
- **Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool. Essa configuração facilitará para os usuários associar um determinado Servidor de Chat Persistente ou pool de Servidor de Chat Persistente com base no nome de exibição, em vez de um mais difícil de entender o nome de domínio totalmente qualificado.
    
- **Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.
    
Edite as **configurações de Associações** para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente definindo ou definindo estas propriedades:
  
 **Associações**
  
- **Sql Server store:** selecione o armazenamento do SQL Server e a instância nomeada opcional na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento principal do SQL Server.
    
    Se você escolher habilitar o espelhamento do armazenamento do SQL Server, selecione o armazenamento e a instância no armazenamento **do SQL Server de espelhamento de lista.**
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento principal do SQL Server.
    
    Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção Usar **armazenamentos** de backup do SQL Server para habilitar a recuperação de desastres se quiser habilitar o uso da recuperação de desastres do SQL Server
    
    Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Backup do SQL Server**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento de espelhamento do SQL Server de backup.
    
    Se você escolher habilitar o espelhamento do armazenamento do SQL Server de backup, selecione o armazenamento e a instância no espelho de **armazenamento do SQL Server de backup da lista.**
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de backup.
    
    Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade
    
    Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **SQL Server store de conformidade**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento do SQL Server de conformidade.
    
    Se você escolher habilitar o espelhamento do armazenamento do SQL Server de conformidade, selecione o armazenamento e a instância no espelho de armazenamento do **SQL Server de conformidade da lista.**
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de conformidade.
    
    Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Backup do SQL Server store de conformidade**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser habilitar o espelhamento para o armazenamento do SQL Server de conformidade.
    
    Se você optar por habilitar o espelhamento do armazenamento do SQL Server de conformidade, selecione o armazenamento e a instância na lista Backup do espelho de armazenamento do **SQL Server de conformidade.**
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar o failover automático se quiser **failover** automático do armazenamento do SQL Server de conformidade de backup.
    
    Se você optar por habilitar a testemunha de espelhamento do armazenamento do SQL Server para habilitar o failover automático, selecione o armazenamento e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- **Armazenamento de arquivos** Selecione um local de armazenamento de arquivos na lista ou clique em **Novo** para criar um novo armazenamento de arquivos.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Plano para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
