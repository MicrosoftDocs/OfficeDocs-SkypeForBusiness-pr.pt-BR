---
title: Adicionar Repositório de Servidor SQL Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados Microsoft SQL Server express e SQL Server banco de dados. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.
ms.openlocfilehash: e369f58afd015953cf0b58ca9788965a4829fd16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119730"
---
# <a name="add-front-end-sql-server-store"></a>Adicionar Front-end do Repositório do SQL Server

Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados Microsoft SQL Server express e SQL Server banco de dados. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.

O pool de Front-End de uma implantação de servidor Enterprise Edition requer uma edição de 64 bits suportada do software de banco de dados SQL Server para o banco de dados back-end. Você pode selecionar um banco de dados de SQL Server definido anteriormente para ser usado para o banco de dados back-end ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão) ou uma instância nomeada que você especificar). Também é possível escolher habilitar o espelhamento no SQL Server store e especificar uma testemunha de espelhamento para failover automático.

Para obter detalhes sobre SQL Server suporte, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) na documentação de Suporte. Para maiores detalhes sobre como configurar um Servidor SQL para o banco de dados back-end, consulte [Configure SQL Server for Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) na documentação de Implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados back-end (comunicação em tempo real (RTC)) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação do Enterprise Edition, você deve ser membro do grupo SQL Server sysadmins para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo SQL Server sysadmins, será necessário solicitar que sejam adicionados ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, deverá fornecer ao administrador do banco de dados SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).