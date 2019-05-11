---
title: Expansor das Configurações Gerais do Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'No Construtor de Topologias, é possível editar as propriedades de um Arquivamento em execução em um servidor individual clicando com o botão direito do mouse no Arquivamento em execução em um servidor individual na árvore de console e clicando em Ação na barra de ferramentas, ou clicando em uma tarefa no painel Ações e clicando emEditar Propriedades e alterando qualquer uma das seguintes opções:'
ms.openlocfilehash: f75614f1720466a4a4d4ba27ef5542e2cfd4036e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887094"
---
# <a name="archiving-server-general-settings-expander"></a>Expansor das Configurações Gerais do Servidor de Arquivamento
 
No Construtor de Topologias, é possível editar as propriedades de um Arquivamento em execução em um servidor individual clicando com o botão direito do mouse no Arquivamento em execução em um servidor individual na árvore de console e clicando em **Ação** na barra de ferramentas, ou clicando em uma tarefa no painel Ações e clicando em**Editar Propriedades** e alterando qualquer uma das seguintes opções:
  
- **FQDN**, para alterar o nome de domínio totalmente qualificado (FQDN) do servidor que você deseja implantar como um Arquivamento em execução no servidor.
    
- **Repositório SQL**, para alterar a instância do SQL Server a ser usada para o banco de dados de arquivamento do SQL Server. Se você alterar o banco de dados do SQL Server de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor.
    
- **Compartilhamento de arquivos**, para alterar a pasta a ser usada para o repositório de arquivamento. Se você alterar o compartilhamento de arquivos de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor. Além disso, é necessário mover os arquivos de conferência anteriores para a nova pasta de repositório de arquivos a fim de evitar perda de arquivos de conferência arquivados.
    
> [!NOTE]
> Para alterar os pools associados ao Arquivamento em execução no servidor, selecione a opção **Editar Propriedades** para o nó do pool de Front-Ends individual ou para o nó do Aparelho de Filial Persistente atualmente associado ao Arquivamento em execução no servidor.
  
> [!NOTE]
> O nó de Arquivamento conterá um Arquivamento em execução no servidor se antes você já tiver adicionado um Arquivamento para execução no servidor à topologia no Construtor de Topologias. É possível editar as propriedades de qualquer servidor que estiver executando o Arquivamento na lista. No entanto, não será possível arquivar mensagens instantâneas ou de webconferência (mensagens) até você configurar o serviço no servidor que estiver executando o Arquivamento. 
  

