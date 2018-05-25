---
title: Criar Banco de Dados
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Construtor de topologia fornece uma maneira para instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologia, o aplicativo lê as informações de topologia e em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisa instalar um banco de dados específico em um computador específico, ou se você deve instalar um banco de dados colocado, você deve usar o cmdlet Install-CsDatabase e interface de linha de comando do Windows PowerShell.
ms.openlocfilehash: 9bee333e0b56a6eeb8f4363e6657be2fabfa1ace
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="create-database"></a>Criar Banco de Dados
 
Construtor de topologia fornece uma maneira para instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologia, o aplicativo lê as informações de topologia e em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisa instalar um banco de dados específico em um computador específico, ou se você deve instalar um banco de dados colocado, você deve usar o cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) e interface de linha de comando do Windows PowerShell.
  
### <a name="creating-a-database"></a>Criando um banco de dados

1. Clique no Skype para Business Server 2015 nó e clique em **Instalar banco de dados**.
    
2. Na caixa de diálogo **Instalar banco de dados** , na página **Criar banco de dados** , selecione o nome de domínio totalmente qualificado (FQDN) do repositório do SQL Server onde os novos bancos de dados devem ser criados.
    
3. Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:
    
  - **Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione essa opção, o Construtor de Topologias utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.
    
  - **Use o SQL Server instância padrões**. Se você selecionar essa opção, o algoritmo incorporado não é usado para escolher os locais de armazenamento para o banco de dados de logs e arquivos de dados. Em vez disso, os arquivos de log e de dados são armazenados nos locais especificados pelo caminho padrões do SQL Server (esses caminhos devem estar configurados no advanced por um administrador do SQL Server). Arquivos de dados serão armazenados no local do arquivo de dados padrão do SQL Server enquanto os arquivos de log serão armazenados no local do arquivo de log padrão do SQL Server.
    
4. Clique em **OK**.
    
5. Na página **Criar banco de dados**, clique em **Avançar**.
    
6. Na página  **Criação de banco de dados concluída**, clique em **Concluir**.
    

