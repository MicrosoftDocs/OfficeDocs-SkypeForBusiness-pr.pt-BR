---
title: Adicionar Repositório de Servidor SQL de Servidor de Monitoramento
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
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: O Monitoring Server requer uma edição de 64 bits suportada SQL Server de banco de dados para armazenar os dados de monitoramento. Você pode selecionar um banco de dados de SQL Server definido anteriormente a ser usado para monitoramento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: b4c5617d125208924554b2420de18c026288ecfc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834259"
---
# <a name="add-monitoring-server-sql-server-store"></a>Adicionar Repositório de Monitoramento do SQL Server

O Monitoring Server requer uma edição de 64 bits suportada SQL Server de banco de dados para armazenar os dados de monitoramento. Você pode selecionar um banco de dados de SQL Server definido anteriormente a ser usado para monitoramento ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir, além da instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

Para obter detalhes SQL Server suporte, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) na documentação de Suporte. Para obter detalhes sobre o banco de dados de monitoramento, incluindo a colocação do banco de dados de monitoramento, consulte Local do Servidor Com Suporte na documentação de[Suporte,](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) Planejamento para Monitoramento na documentação de Planejamento e [](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) Posicionamento de Arquivos de Dados e Log na documentação de Implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de monitoramento ao publicar sua topologia. Você também pode criar o banco de dados mais tarde como parte, inclusive, do procedimento de instalação. > Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo SQL Server sysadmins para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo SQL Server sysadmin, será necessário solicitar que sejam adicionados ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, deverá fornecer ao administrador do banco de dados SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar esses procedimentos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) na documentação Implantação.