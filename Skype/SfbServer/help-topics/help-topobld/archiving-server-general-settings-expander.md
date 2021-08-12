---
title: Expansor das Configurações Gerais do Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'No Construtor de Topologias, você pode editar as propriedades de um servidor individual executando o Arquivamento clicando com o botão direito do mouse no servidor que executa o Arquivamento na árvore de console e clicando em Ação na barra de ferramentas ou clicando em uma tarefa no painel Ações e clicando em Editar Propriedades e alterando qualquer uma das seguintes opções:'
ms.openlocfilehash: 4f33daa968bea70b210952e818fd81354f71ec786ff1196cb1e762d6b65bd61c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301537"
---
# <a name="archiving-server-general-settings-expander"></a>Expansor das Configurações Gerais do Servidor de Arquivamento
 
No Construtor de Topologias, você pode editar as propriedades de um servidor individual executando o Arquivamento clicando com o botão direito do mouse no servidor que executa o Arquivamento na árvore de console e clicando em **Ação** na barra de ferramentas ou clicando em uma tarefa no painel Ações e clicando em **Editar Propriedades** e alterando qualquer uma das seguintes opções:
  
- **FQDN**, para alterar o nome de domínio totalmente qualificado (FQDN) do servidor que você deseja implantar como um Arquivamento em execução no servidor.
    
- **Repositório SQL**, para alterar a instância do SQL Server a ser usada para o banco de dados de arquivamento do SQL Server. Se você alterar o banco de dados do SQL Server de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor.
    
- **Compartilhamento de arquivo**, para alterar a pasta a ser usada para o repositório de arquivamento. Se você alterar o compartilhamento de arquivos de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor. Além disso, é necessário mover os arquivos de conferência anteriores para a nova pasta de repositório de arquivos a fim de evitar perda de arquivos de conferência arquivados.
    
> [!NOTE]
> Para alterar os pools associados ao Arquivamento em execução no servidor, selecione a opção **Editar Propriedades** para o nó do pool Front End individual ou o nó Aparelho de Filial Persistente atualmente associado ao Arquivamento em execução no servidor.
  
> [!NOTE]
> O nó Arquivamento conterá um Arquivamento em execução no servidor se você tiver adicionado anteriormente um Arquivamento em execução no servidor à topologia no Construtor de Topologia. É possível editar as propriedades de qualquer Arquivamento em execução no servidor na lista. No entanto, mensagens instantâneas ou webconferência (mensagens) não podem ser arquivadas até que você também configurar o serviço para o servidor que está executando o Arquivamento. 
  

