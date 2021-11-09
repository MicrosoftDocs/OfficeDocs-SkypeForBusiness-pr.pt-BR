---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Na página Executando comandos, as tarefas de instalação do SQL Server Express e configuração para atuar como o armazenamento de Gerenciamento Central podem ser exibidas no painel de tarefas. Por padrão, uma instância de um banco de dados SQL Server baseado em SQL Server chamado RTC é criada. Regras de firewall também são criadas para permitir acesso de entrada e saída aos servidores e clientes para comunicação com o banco de dados e a instância. Após a conclusão da tarefa, será possível selecionar o arquivo de log na lista suspensa. O arquivo de log é chamado de  Máquina local de inicialização . Após selecionar o arquivo de log, clique em  Exibir Log . Verifique se há erros e avisos no arquivo de log. Quando estiver pronto para prosseguir, clique em  Concluir . Agora, você deve definir sua topologia com o Construtor de Topologias se ainda não tiver feito isso.
ms.openlocfilehash: 8d72d69b8c5ea676bf1e944bda143ad8f56fea82
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841583"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar Servidor Standard Edition Único (Invocar)
 
Na página **Executando comandos,** as tarefas de instalação do SQL Server Express e configuração para atuar como o armazenamento de Gerenciamento Central podem ser exibidas no painel de tarefas. Por padrão, uma instância de um banco de dados SQL Server baseado em SQL Server chamado RTC é criada. Regras de firewall também são criadas para permitir acesso de entrada e saída aos servidores e clientes para comunicação com o banco de dados e a instância. Após a conclusão da tarefa, será possível selecionar o arquivo de log na lista suspensa. O arquivo de log é chamado de  **Máquina local de inicialização**. Após selecionar o arquivo de log, clique em  **Exibir Log**. Verifique se há erros e avisos no arquivo de log. Quando estiver pronto para prosseguir, clique em  **Concluir**. Agora, você deve definir sua topologia com o Construtor de Topologias se ainda não tiver feito isso.
  
> [!IMPORTANT]
> A instalação do SQL Server Express pode levar algum tempo para ser concluída. Não existe um progresso visível na tela ou painel de tarefas durante a instalação. Para monitorar a instalação, você deve usar Windows Task Manager e procurar os processos MSIExec e os arquivos de Instalação para SQL Server. Você pode, dessa maneira, visualizar o status da instalação e certificar-se de que a instalação está prosseguindo. Dependendo de fatores além do escopo deste tópico de ajuda, pode levar até 15 minutos ou mais para a instalação da instância SQL Server ser concluída. 
  

