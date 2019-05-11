---
title: Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Resumo: Saiba como associar pools de Front-End com um repositório de monitoramento usado pelo Skype para Business Server.'
ms.openlocfilehash: 0b6b30955b22fdd330f72f0aa9719e8b887663f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894574"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server 
**Resumo:** Saiba como associar pools de Front-End com um repositório de monitoramento usado pelo Skype para Business Server.
  
No Skype para Business Server, dados de monitoramento só podem ser obtidos em pools de Front-End que tenham sido associados um repositório de monitoramento, uma tarefa que normalmente executada quando você definir um pool de Front-End no construtor de topologia.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associar um repositório de monitoramento ao pool de front-ends

 Para associar um repositório de monitoramento a um novo pool de front-ends, selecione a opção **Monitoramento (registro de detalhes da chamada e registro das métricas de qualidade de experiência)** na página **Selecionar recursos** do assistente Definir novo pool de front-ends. Observe que, se você selecionar essa opção, será necessário também especificar um repositório SQL para concluir o assistente. No entanto, esse repositório precisa existir no momento da execução do assistente. Isso significa que você pode primeiro associar um pool a um repositório de monitoramento e, depois, instalar e configurar esse repositório.
  
Em alternativa, é possível associar um pool de front-ends existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:
  
1. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para o construtor de topologia de servidor de negócios**.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar como**, insira um nome de arquivo para sua topologia atual e clique em **Salvar**. A topologia salva poderá ser recuperada posteriormente e republicada em caso que haja problemas com a nova topologia.
    
4. No construtor de topologia, expanda **Skype para Business Server**, expanda o nome do site contendo o pool de Front-End e expanda **pools de Front End do Enterprise Edition**.
    
5. Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar propriedades**.
    
6. Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas de QoE)** e selecione um banco de dados existente do SQL Server na lista suspensa **Monitoramento do repositório do SQL Server**. (Você também pode clicar em **Novo** para associar o pool a um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do SQL Server**. Se você deseja usar a instância padrão do SQL Server para esse repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.
    
    A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outra no computador do espelho SQL). Para habilitar o espelhamento, selecione T **sua instância do SQL está em relação de espelhamento** e digite o número da porta do servidor de espelho na caixa **número da porta de espelhamento** .
    
7. Na caixa de diálogo **Editar propriedades**, clique em **OK**.
    
Após associar o repositório de monitoramento a um pool de front-ends, você deverá publicar a nova topologia antes de as alterações entrarem em vigor. Para publicar sua topologia nova, conclua as etapas a seguir no construtor de topologia:
  
1. Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.
    
2. No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que hospedará o repositório de monitoramento. O banco de dados de monitoramento pode ser instalado usando o Skype para o Shell de gerenciamento do Business Server e o Windows PowerShell. Para instalar o banco de dados localmente (isto é, para instalar o banco de dados no mesmo computador onde você está executando o Skype do Shell de gerenciamento do servidor de negócios), inicie o Shell de gerenciamento no computador apropriado, digite o seguinte comando e pressione ENTER:
  
```
Install-CsDatabase -LocalDatabases
```

Quando você executa o comando anterior, Install-CsDatabase será ler o Skype atual para a topologia de servidor de negócios, determine quais bancos de dados precisam ser instalado no computador local e, em seguida, instalar e configurar automaticamente cada um desses bancos de dados.
  
Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn. Esses parâmetros informam o cmdlet Install-CsDatabase para recuperar o Skype para a topologia de servidor de negócios e, em seguida, instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn. O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.
  
Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, você pode instalar o banco de dados de monitoramento, executando o Skype para o Assistente de implantação do Business Server no computador que hospedará o repositório de monitoramento. Para fazer isso, faça o login no computador em questão e conclua o seguinte procedimento:
  
1. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para o Assistente de implantação de servidor de negócios**.
    
2. No Assistente de implantação, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**.
    
3. Na página **implantar** , sob **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Executar novamente**.
    
4. No Skype a instalação para o Assistente de componentes do servidor de negócios, na página **Instalação Skype para componentes de servidor de negócios** , clique em **Avançar**.
    
5. Na página **Especificar caminho para MSIs** , digite o caminho para o arquivo ocscore. msi (um arquivo incluído com sua Skype para a mídia de instalação do Business Server) e clique em **Avançar**.
    
6. Na página **Executando comandos** clique em **Concluir**.
    
Para garantir que todos o Skype necessário para serviços de Business Server foram iniciados, clique em **Executar** sob o título **etapa 4: iniciar serviços** na página **implantar**
  

