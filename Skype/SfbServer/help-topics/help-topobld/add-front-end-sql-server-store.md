---
title: Adicionar Repositório de Servidor SQL Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados do Microsoft SQL Server Express necessário e o banco de dados do SQL Server. Portanto, todas as opções são preenchidas previamente e não é possível fazer alterações na configuração padrão.
ms.openlocfilehash: 865f9a63902124c57232ba8d8c591622dcbfd84a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820813"
---
# <a name="add-front-end-sql-server-store"></a>Adicionar Repositório de Servidor SQL Front End

Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados do Microsoft SQL Server Express necessário e o banco de dados do SQL Server. Portanto, todas as opções são preenchidas previamente e não é possível fazer alterações na configuração padrão.

O pool de front-end de uma implantação do servidor Enterprise Edition requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para o banco de dados back-end. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para o banco de dados back-end, ou definir um novo banco de dados SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server está para ficar e a instância do SQL S ervidor que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar). Você também pode optar por habilitar o espelhamento na loja do SQL Server e especificar uma testemunha de espelhamento para failover automático.

Para obter detalhes sobre o suporte do SQL Server, consulte [suporte a cluster e software de banco de dados](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de suporte. Para obter detalhes sobre a configuração do SQL Server para o banco de dados back-end, consulte [Configurar o SQL Server para Lync server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) na documentação de implantação.

> [!NOTE]
> Se a conta que é usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados back-end (RTC) quando publicar sua topologia. Você também pode criar o banco de dados posteriormente, incluindo como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação do Enterprise Edition, você deve ser um membro do grupo Administradores do SQL Server para o servidor baseado no SQL Server no qual está instalando os arquivos do banco de dados. Se você não for membro do grupo Administradores do SQL Server, será necessário solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados. Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões de usuário que você precisa para executar os procedimentos, consulte [permissões de implantação para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


