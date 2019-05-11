---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Na página executando comandos, as tarefas de instalação do SQL Server Express e configurando para agir como o repositório de gerenciamento Central podem ser exibidas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server denominada RTC é criada. Regras de firewall também são criadas para permitir o acesso de entrada e saído para servidores e clientes para se comunicar com o banco de dados e a instância. Quando a tarefa for concluída, você pode selecionar o arquivo de log da lista suspensa. O arquivo de log é chamado de Bootstrap máquina local. Depois de selecionar o arquivo de log, clique em Exibir Log. Revise o arquivo de log para quaisquer erros e avisos. Quando você estiver pronto para prosseguir, clique em Concluir. Agora você deve definir sua topologia com o construtor de topologias, se você ainda não tiver feito isso.
ms.openlocfilehash: fad1a7e4ab611ccf8ee152bf24c1eb1898d9cd51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910718"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar Servidor Standard Edition Único (Invocar)
 
Na página **executando comandos** , as tarefas de instalação do SQL Server Express e configurando para agir como o repositório de gerenciamento Central podem ser exibidas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server denominada RTC é criada. Regras de firewall também são criadas para permitir o acesso de entrada e saído para servidores e clientes para se comunicar com o banco de dados e a instância. Quando a tarefa for concluída, você pode selecionar o arquivo de log da lista suspensa. O arquivo de log é chamado de **Bootstrap máquina local**. Depois de selecionar o arquivo de log, clique em **Exibir Log**. Revise o arquivo de log para quaisquer erros e avisos. Quando você estiver pronto para prosseguir, clique em **término.** Agora você deve definir sua topologia com o construtor de topologias, se você ainda não tiver feito isso.
  
> [!IMPORTANT]
> A instalação do SQL Server Express pode levar algum tempo para ser concluída. Durante a instalação, não há nenhum progresso visível na tela ou o painel de tarefas. Para monitorar a instalação, você deve usar o Gerenciador de tarefas do Windows e procure os processos de MSIExec e os arquivos de instalação para o SQL Server. Dessa forma, você pode exibir o status da instalação e certifique-se de que a instalação está prosseguindo. Dependendo de fatores além do escopo deste tópico de Ajuda, ele pode demorar até 15 minutos ou mais para a instalar o SQL Server de instância para concluir. 
  

