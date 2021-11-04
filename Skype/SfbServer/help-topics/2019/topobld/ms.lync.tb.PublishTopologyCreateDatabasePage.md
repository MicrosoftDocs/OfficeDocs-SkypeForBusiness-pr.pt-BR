---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: O Construtor de Topologias fornece uma maneira de instalar bancos de dados em um SQL Server store. Quando você instala bancos de dados usando o Construtor de Topologias, o aplicativo lê informações da topologia e instala os bancos de dados necessários no computador SQL Server ou no cluster SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se você precisar instalar um banco de dados específico em um computador específico ou se precisar instalar um banco de dados alocado, deverá usar uma interface de linha de comando Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: d864f469d9200040c61611a70f81c442cfdb7269
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759903"
---
# <a name="create-database"></a>Criar banco de dados
 
O Construtor de Topologias fornece uma maneira de instalar bancos de dados em um SQL Server store. Quando você instala bancos de dados usando o Construtor de Topologias, o aplicativo lê informações da topologia e instala os bancos de dados necessários no computador SQL Server ou no cluster SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se você precisar instalar um banco de dados específico em um computador específico ou se precisar instalar um banco de dados alocado, deverá usar uma interface de linha de comando Windows PowerShell e o cmdlet [Install-CsDatabase.](/powershell/module/skype/install-csdatabase?view=skype-ps)
  
### <a name="creating-a-database"></a>Criando um Banco de Dados

1. Clique no nó Skype for Business Server e clique em **Instalar Banco de Dados**.
    
2. Na  caixa de diálogo Instalar  Bancos de Dados, na página Criar Banco de Dados, selecione o nome de domínio totalmente qualificado (FQDN) do armazenamento SQL Server onde os novos bancos de dados devem ser criados.
    
3. Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:
    
   - **Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione esta opção, o Construtor de Topologia utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.
    
   - **Use SQL Server de instância.** Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento para os logs de banco de dados e os arquivos de dados. Em vez disso, o registro e os arquivos de dados serão armazenados nos locais especificados pelo caminho padrão do SQL Server (esses caminhos devem ser configurados antecipadamente por um administrador do SQL Server). Os arquivos de dados devem ser armazenados no local padrão para os arquivos de dados do SQL, enquanto os arquivos de registro são armazenados no local padrão para os arquivos de registro do SQL Server.
    
4. Clique em **OK**.
    
5. Na página **Criar Banco de Dados**, clique em **Próximo**.
    
6. Na página **Criação de Banco de Dados Concluída**, clique em **Concluir**.
