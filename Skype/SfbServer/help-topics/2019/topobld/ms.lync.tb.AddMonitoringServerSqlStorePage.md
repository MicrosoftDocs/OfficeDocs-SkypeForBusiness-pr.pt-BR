---
title: Adicionar Repositório de Servidor SQL de Servidor de Monitoramento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: O Monitoring Server requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para armazenar os dados de monitoramento. Você pode selecionar um banco de dados do SQL Server definido anteriormente a serem usados para monitoramento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residem, além da instância do SQL Servidor que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 4ecbdac4b78c4a377d3de17a136e031ee7503582
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888783"
---
# <a name="add-monitoring-server-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Servidor de Monitoramento

O Monitoring Server requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para armazenar os dados de monitoramento. Você pode selecionar um banco de dados do SQL Server definido anteriormente a serem usados para monitoramento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residem, além da instância do SQL Servidor que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

Para obter detalhes sobre SQL Server suporte, consulte o [Software de banco de dados e suporte a clusters](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de suporte. Para obter detalhes sobre o monitoramento banco de dados, incluindo a colocação do banco de dados de monitoramento, consulte [Suporte para o local do servidor](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de suporte,[Planejando o monitoramento](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) na documentação de planejamento e [dados do SQL Server e a localização do arquivo de Log](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de monitoramento ao publicar sua topologia. Também é possível criar o banco de dados mais tarde, incluindo como parte do procedimento de instalação. gt _ instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for um membro do grupo sysadmin do SQL Server, você deverá solicitar a ser adicionado ao grupo até que os arquivos de banco de dados são implantados. Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões necessárias para realizar esses procedimentos, consulte [Permissões de implantação para o SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


