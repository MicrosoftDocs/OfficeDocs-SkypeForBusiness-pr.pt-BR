---
title: Adicionar repositório de arquivamento Front-End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residir, além da instância do SQL Se servidor & que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: b8d5a46f0eeebca36bfb8c355a32d61f477564e7
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261774"
---
# <a name="add-front-end-archiving-store"></a>Adicionar repositório de arquivamento Front-End

O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residir, além da instância do SQL Se servidor & que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).

> [!NOTE]
> Se a conta usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de monitoramento ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.

> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não for um membro do grupo sysadmin do SQL Server, você deverá solicitar que você ser adicionado ao grupo até que os arquivos de banco de dados são implantados. Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões necessárias para realizar os procedimentos, consulte [Permissões de implantação para o SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.


