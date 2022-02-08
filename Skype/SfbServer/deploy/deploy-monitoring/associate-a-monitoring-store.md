---
title: Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Resumo: saiba como associar pools de Front-End a um armazenamento de monitoramento usado por Skype for Business Server.'
ms.openlocfilehash: 0092b75d35f97a7224e8946e24257c5f8ee6ea0d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385229"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server 
**Resumo:** Saiba como associar pools de Front-End a um armazenamento de monitoramento usado por Skype for Business Server.
  
No Skype for Business Server, os dados de monitoramento só podem ser coletados em pools de Front-End associados a um armazenamento de monitoramento, uma tarefa normalmente realizada quando você define um pool de Front-End no Construtor de Topologias.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associar um armazenamento de monitoramento a um pool de Front-End

 Para associar um armazenamento de monitoramento a um novo pool de Front-End, selecione a opção Monitoramento (registro de detalhes de chamada e registro em log de **métricas** de qualidade da experiência)  na página Selecionar Recursos do assistente Definir Novo Pool de Front-End. Observe que, se você selecionar essa opção, também deverá especificar um SQL para concluir o assistente; no entanto, esse armazenamento não precisa existir no momento em que você executar o assistente. Isso significa que você pode primeiro associar um pool a um armazenamento de monitoramento, depois configurar e configurar esse armazenamento posteriormente.
  
Em alternativa, é possível associar um pool de front-end existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:
  
1. Clique **em Iniciar**, **em Todos os Programas**, **Skype for Business Server 2015** e clique **Skype for Business Server Construtor de Topologias**.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar como**, insira um nome de arquivo da sua topologia atual e clique em **Salvar**. A topologia salva pode ser recuperada posteriormente e republicada em caso que hajam problemas com a nova topologia.
    
4. No Construtor de Topologias, **expanda Skype for Business Server**, expanda o nome do site que contém o pool de Front-End e clique em expandir Edição Enterprise **pools de Front-End**.
    
5. Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar Propriedades**.
    
6. Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas QoE)** e selecione um banco de dados existente do SQL Server da lista suspensa **Monitoramento do repositório do SQL Server**. (Em alternativa, clique em **Novo** para associar o pool com um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do Sql Server**. Se você deseja usar a instância padrão do SQL Server para este repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.
    
    A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outro no computador do SQL espelho). Para habilitar o espelhamento, selecione T **sua instância SQL** está em relação de espelhamento e insira o número da porta para o servidor espelho na caixa Número da porta **espelhamento**.
    
7. Na caixa de diálogo **Editar propriedades**, clique em **OK**.
    
Após associar o repositório de monitoramento com um pool de front-end, você deve publicar a nova topologia antes das alterações entrarem em vigor. Para publicar sua nova topologia, conclua as seguintes etapas no Construtor de Topologia:
  
1. Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.
    
2. No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Publicar assistente concluído**, clique em **Concluir**.
    
Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que irá hospedar o repositório de monitoramento. O banco de dados de monitoramento pode ser instalado usando o Shell de Gerenciamento Skype for Business Server e Windows PowerShell. Para instalar o banco de dados localmente (ou seja, para instalar o banco de dados no mesmo computador em que você está executando o Shell de Gerenciamento do Skype for Business Server), inicie o Shell de Gerenciamento no computador apropriado e digite o seguinte comando e pressione ENTER:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Quando você executar o comando anterior, Install-CsDatabase lerá Skype for Business Server topologia atual, determinará quais bancos de dados precisam ser instalados no computador local e instalará e configurará automaticamente cada um desses bancos de dados.
  
Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn. Esses parâmetros informam ao cmdlet Install-CsDatabase para recuperar Skype for Business Server topologia do Skype for Business Server e instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn. O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.
  
Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, você pode instalar o banco de dados de monitoramento executando o Assistente de Implantação Skype for Business Server no computador que hospedará o armazenamento de monitoramento. Para fazer isso, faça o login no computador adequado e conclua o seguinte procedimento:
  
1. Clique **em Iniciar**, em **Todos os Programas**, **Skype for Business Server 2015** e clique **Skype for Business Server Assistente de Implantação**.
    
2. No Assistente de Implantação, clique **em Instalar ou Atualizar Skype for Business Server Sistema**.
    
3. Na página **Implantar**, em **Etapa 2: Configurar ou Remover Skype for Business Server Componentes**, clique em **Executar Novamente**.
    
4. No assistente de instalação Skype for Business Server componentes, na página **Configuração Skype for Business Server componentes**, clique em **Próximo**.
    
5. Na página **Especificar caminho para MSIs**, digite o caminho para o arquivo Ocscore.msi (um arquivo incluído com sua mídia de instalação Skype for Business Server) e clique em **Próximo**.
    
6. Na página **Executando Comandos**, clique em **Concluir**.
    
Para garantir que todos os serviços de Skype for Business Server necessários tenham sido iniciados, clique  em Executar sob o título **Etapa 4: Iniciar Serviços** na página **Implantar**
  

