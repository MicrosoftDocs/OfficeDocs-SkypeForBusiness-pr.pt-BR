---
title: Adicionar Repositório de Servidor SQL Front End
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Uma Edição Standard de servidor instala automaticamente o software Microsoft SQL Server Express de banco de dados e o banco de dados SQL Server de dados. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.
ms.openlocfilehash: eaa6b6f313632fe3b0acfc5d89a0117978cced42
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835709"
---
# <a name="add-front-end-sql-server-store"></a>Adicionar Front-end do Repositório do SQL Server

Uma Edição Standard de servidor instala automaticamente o software Microsoft SQL Server Express de banco de dados e o banco de dados SQL Server de dados. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.

O pool de Front-End de uma implantação de servidor Edição Enterprise requer uma edição de 64 bits suportada do software de banco de dados SQL Server para o banco de dados back-end. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para o banco de dados back-end ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar). Também é possível escolher habilitar o espelhamento no SQL Server store e especificar uma testemunha de espelhamento para failover automático.

Para obter detalhes SQL Server suporte, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) na documentação de Suporte. Para obter detalhes sobre como configurar SQL Server para o banco de dados back-end, consulte [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) na documentação implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados back-end (comunicação em tempo real (RTC)) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação do Edição Enterprise, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server em que você está instalando os arquivos de banco de dados. Se você não for membro do grupo SQL Server sysadmins, será necessário solicitar que sejam adicionados ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, deverá fornecer ao administrador do banco de dados SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).