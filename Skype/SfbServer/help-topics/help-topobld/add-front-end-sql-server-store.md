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
description: Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados microsoft SQL Server Express necessário e o banco de dados do SQL Server. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.
ms.openlocfilehash: 939f12fa02951074e487066337c8bb76af59143a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824071"
---
# <a name="add-front-end-sql-server-store"></a>Adicionar Front-end do Repositório do SQL Server

Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados microsoft SQL Server Express necessário e o banco de dados do SQL Server. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.

O pool #A0 de uma implantação de servidor Enterprise Edition requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para o banco de dados back-end. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para o banco de dados back-end ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você). Também é possível escolher habilitar o espelhamento no SQL Server store e especificar uma testemunha de espelhamento para failover automático.

Para obter detalhes sobre o suporte ao SQL Server, consulte [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de Suporte. Para maiores detalhes sobre como configurar um Servidor SQL para o banco de dados back-end, consulte [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) na documentação de Implantação.

> [!NOTE]
> Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados back-end (comunicação em tempo real (RTC)) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação Enterprise Edition, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for membro do grupo sysadmins do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


