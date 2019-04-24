---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Servidor de arquivamento requer uma edição de 64 bits com suporte de software de banco de dados do SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server previamente definido para ser usado para arquivamento ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual residirá o banco de dados do SQL Server e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: f16a405551822041ad7d792ac9307e29df19ee45
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202293"
---
# <a name="add-archiving-server-sql-server-store"></a>Adicionar Repositório de Servidor SQL para Servidor de Arquivamento

Servidor de arquivamento requer uma edição de 64 bits com suporte de software de banco de dados do SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server previamente definido para ser usado para arquivamento ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual residirá o banco de dados do SQL Server e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta que é usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de arquivamento (LcsLog) quando você publica sua topologia. Também é possível criar o banco de dados mais tarde, como parte do procedimento de instalação, ou outra forma.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não é um membro do grupo de sysadmins do SQL Server, você deverá solicitar a ser adicionado ao grupo até que os arquivos de banco de dados são implantados. Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões necessárias para realizar os procedimentos, consulte [Permissões de implantação para o SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


