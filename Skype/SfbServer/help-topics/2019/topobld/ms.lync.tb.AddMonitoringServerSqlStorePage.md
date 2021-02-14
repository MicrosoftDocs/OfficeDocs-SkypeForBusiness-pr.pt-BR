---
title: Adicionar Repositório de Servidor SQL de Servidor de Monitoramento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: O Monitoring Server requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de monitoramento. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para monitoramento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados sql Server irá residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).
ms.openlocfilehash: a96dced5bfae5e8381ea28874d295dcfe146d33e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807731"
---
# <a name="add-monitoring-server-sql-server-store"></a>Adicionar Repositório de Monitoramento do SQL Server

O Monitoring Server requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de monitoramento. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para monitoramento ou definir um novo banco de dados do SQL Server especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados sql Server irá residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).

Para obter detalhes sobre o suporte ao SQL Server, consulte [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de Suporte. Para obter detalhes sobre o banco de dados de monitoramento, incluindo a colocação do banco de dados de monitoramento, consulte [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de monitoramento ao publicar sua topologia. Você também pode criar o banco de dados mais tarde como parte, inclusive, do procedimento de instalação. > Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo sysadmin do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar esses procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.


