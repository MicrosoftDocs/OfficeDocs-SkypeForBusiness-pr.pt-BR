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
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: O construtor de topologias oferece uma maneira de instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se for necessário instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados colocado, você deverá usar a interface de linha de comando do Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219502"
---
# <a name="create-database"></a>Criar banco de dados
 
O construtor de topologias oferece uma maneira de instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se for necessário instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados colocado, você deverá usar a interface de linha de comando do Windows PowerShell e o cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .
  
### <a name="creating-a-database"></a>Criando um Banco de Dados

1. Clique no nó do Skype for Business Server 2015 e, em seguida, clique em **instalar banco de dados**.
    
2. Na caixa de diálogo **instalar bancos** de dados, na página **criar banco de dados** , selecione o FQDN (nome de domínio totalmente qualificado) do repositório do SQL Server onde os novos bancos de dados serão criados.
    
3. Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:
    
   - **Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione esta opção, o Construtor de Topologia utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.
    
   - **Usar padrões de instância do SQL Server**. Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento dos logs e dos arquivos de dados do banco de dados. Em vez disso, o registro e os arquivos de dados serão armazenados nos locais especificados pelo caminho padrão do SQL Server (esses caminhos devem ser configurados antecipadamente por um administrador do SQL Server). Os arquivos de dados devem ser armazenados no local padrão para os arquivos de dados do SQL, enquanto os arquivos de registro são armazenados no local padrão para os arquivos de registro do SQL Server.
    
4. Clique em **OK**.
    
5. Na página **Criar Banco de Dados**, clique em **Próximo**.
    
6. Na página**Criação de Banco de Dados Concluída**, clique em **Concluir**.
    

