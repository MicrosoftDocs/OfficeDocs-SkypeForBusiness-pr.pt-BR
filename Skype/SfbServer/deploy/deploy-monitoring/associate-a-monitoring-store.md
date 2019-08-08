---
title: Associar um repositório de monitoramento a um pool de front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Resumo: saiba como associar pools de front-end a um repositório de monitoramento usado pelo Skype for Business Server.'
ms.openlocfilehash: 66d51e89a41c5e6ce2608b4fe8ecd1c4af336b6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239987"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associar um repositório de monitoramento a um pool de front-end no Skype for Business Server 
**Resumo:** Saiba como associar pools de front-end a um repositório de monitoramento usado pelo Skype for Business Server.
  
No Skype for Business Server, os dados de monitoramento só podem ser coletados em pools front-ends que foram associados a uma loja de monitoramento, uma tarefa geralmente realizada quando você define um pool de front-end no construtor de topologias.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associar um repositório de monitoramento ao pool de front-ends

 Para associar um repositório de monitoramento a um novo pool de front-ends, selecione a opção **Monitoramento (registro de detalhes da chamada e registro das métricas de qualidade de experiência)** na página **Selecionar recursos** do assistente Definir novo pool de front-ends. Observe que, se você selecionar essa opção, será necessário também especificar um repositório SQL para concluir o assistente. No entanto, esse repositório precisa existir no momento da execução do assistente. Isso significa que você pode primeiro associar um pool a um repositório de monitoramento e, depois, instalar e configurar esse repositório.
  
Em alternativa, é possível associar um pool de front-ends existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:
  
1. Clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server 2015**e, em seguida, clique em **Construtor de topologia do Skype for Business Server**.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar como**, insira um nome de arquivo para sua topologia atual e clique em **Salvar**. A topologia salva poderá ser recuperada posteriormente e republicada em caso que haja problemas com a nova topologia.
    
4. No construtor de topologias, expanda o **Skype for Business Server**, expanda o nome do site que contém o pool de front-ends e clique em expandir **grupos de front-end Enterprise Edition**.
    
5. Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar propriedades**.
    
6. Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas de QoE)** e selecione um banco de dados existente do SQL Server na lista suspensa **Monitoramento do repositório do SQL Server**. (Você também pode clicar em **Novo** para associar o pool a um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do SQL Server**. Se você deseja usar a instância padrão do SQL Server para esse repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.
    
    A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outra no computador do espelho SQL). Para habilitar o espelhamento, selecione T **sua instância SQL está na relação espelhada** e insira o número da porta do servidor espelho na caixa **número da porta** de espelhamento.
    
7. Na caixa de diálogo **Editar propriedades**, clique em **OK**.
    
Após associar o repositório de monitoramento a um pool de front-ends, você deverá publicar a nova topologia antes de as alterações entrarem em vigor. Para publicar sua nova topologia, complete as seguintes etapas no construtor de topologias:
  
1. Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.
    
2. No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que hospedará o repositório de monitoramento. O banco de dados de monitoramento pode ser instalado usando o Shell de gerenciamento do Skype for Business Server e o Windows PowerShell. Para instalar o banco de dados localmente (ou seja, instalar o banco de dados no mesmo computador em que você está executando o Shell de gerenciamento do Skype for Business Server), inicie o Shell de gerenciamento no computador apropriado e, em seguida, digite o seguinte comando e pressione ENTER:
  
```
Install-CsDatabase -LocalDatabases
```

Quando você executar o comando anterior, install-CsDatabase lerá a topologia atual do Skype for Business Server, determinará quais bancos de dados precisam ser instalados no computador local e, em seguida, instalar e configurar automaticamente cada um desses bancos de dados.
  
Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn. Esses parâmetros dizem ao cmdlet Install-CsDatabase para recuperar a topologia do Skype for Business Server e, em seguida, instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn. O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.
  
Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Você também pode instalar o banco de dados de monitoramento executando o assistente de implantação do Skype for Business Server no computador que hospedará a loja de monitoramento. Para fazer isso, faça o login no computador em questão e conclua o seguinte procedimento:
  
1. Clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server 2015**e, em seguida, clique em **Assistente de implantação do Skype for Business Server**.
    
2. No assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server**.
    
3. Na página **implantar** , em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique **novamente em executar**.
    
4. No assistente configurar o Skype for Business Server Components, na página **Configure o Skype for Business Server Components** , clique em **Avançar**.
    
5. Na página **especificar caminho para MSIs** , digite o caminho para o arquivo OCScore. msi (um arquivo incluído na mídia de instalação do Skype for Business Server) e clique em **Avançar**.
    
6. Na página **Executando comandos** clique em **Concluir**.
    
Para garantir que todos os serviços do Skype for Business Server necessários tenham começado, clique em **executar** abaixo do título **etapa 4: Iniciar serviços** na página **implantar**
  

