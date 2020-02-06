---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Na página comandos em execução, as tarefas de instalação do SQL Server Express e da configuração para atuar como o repositório de gerenciamento central podem ser visualizadas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada. As regras de firewall também são criadas para permitir acesso de entrada e saída para servidores e clientes para se comunicar com o banco de dados e a instância. Após a conclusão da tarefa, você pode selecionar o arquivo de registro na lista suspensa. O arquivo de log é chamado máquina local de inicialização. Depois de selecionar o arquivo de registro, clique em Exibir log. Examine o arquivo de log para ver se há erros e avisos. Quando estiver pronto para continuar, clique em concluir. Agora, você deve definir sua topologia com o construtor de topologias se ainda não tiver feito isso.
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796962"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar Servidor Standard Edition Único (Invocar)
 
Na página **comandos em execução** , as tarefas de instalação do SQL Server Express e da configuração para atuar como o repositório de gerenciamento central podem ser visualizadas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada. As regras de firewall também são criadas para permitir acesso de entrada e saída para servidores e clientes para se comunicar com o banco de dados e a instância. Após a conclusão da tarefa, você pode selecionar o arquivo de registro na lista suspensa. O arquivo de log é chamado **máquina local de inicialização**. Depois de selecionar o arquivo de registro, clique em **Exibir log**. Examine o arquivo de log para ver se há erros e avisos. Quando estiver pronto para continuar, clique em **concluir.** Agora, você deve definir sua topologia com o construtor de topologias se ainda não tiver feito isso.
  
> [!IMPORTANT]
> A instalação do SQL Server Express pode levar algum tempo para ser concluída. Durante a instalação, não há progresso visível na tela ou no painel de tarefas. Para monitorar a instalação, você deve usar o Gerenciador de tarefas do Windows e procurar os processos MSIExec e os arquivos de instalação do SQL Server. Dessa forma, você pode ver o status da instalação e ter certeza de que a instalação está continuando. Dependendo dos fatores além do escopo deste tópico da ajuda, pode levar até 15 minutos ou mais para instalar a instância do SQL Server para ser concluída. 
  

