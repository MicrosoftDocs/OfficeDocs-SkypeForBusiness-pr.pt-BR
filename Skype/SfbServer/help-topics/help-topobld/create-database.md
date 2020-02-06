---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: O construtor de topologias fornece uma maneira de instalar bancos de dados em uma loja do SQL Server. Ao instalar bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisar instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados posicionado, você deve usar a interface de linha de comando do Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: cd3bd6e24f0dc3ec21c5cfa8626d9696454855e7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820233"
---
# <a name="create-database"></a>Criar Banco de Dados
 
O construtor de topologias fornece uma maneira de instalar bancos de dados em uma loja do SQL Server. Ao instalar bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisar instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados posicionado, você deve usar a interface de linha de comando do Windows PowerShell e o cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Criando um banco de dados

1. Clique no nó Skype for Business Server 2015 e, em seguida, clique em **instalar banco de dados**.
    
2. Na caixa de diálogo **instalar bancos** de dados, na página **criar banco de dados** , selecione o nome de domínio totalmente qualificado (FQDN) da loja do SQL Server em que os novos bancos de dados devem ser criados.
    
3. Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:
    
   - **Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione essa opção, o Construtor de Topologias utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.
    
   - **Usar padrões de instância do SQL Server**. Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento dos logs e dos arquivos de dados do banco de dados. Em vez disso, os arquivos de log e dados são armazenados nos locais especificados pelo caminho de padrões do SQL Server (esses caminhos devem ser configurados em avançado por um administrador do SQL Server). Os arquivos de dados serão armazenados no local padrão do arquivo de dados do SQL Server enquanto os arquivos de log serão armazenados no local padrão do arquivo de log do SQL Server.
    
4. Clique em **OK**.
    
5. Na página **Criar banco de dados**, clique em **Avançar**.
    
6. Na página  **Criação de banco de dados concluída**, clique em **Concluir**.
    

