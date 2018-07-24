---
title: Adicionar repositório de servidor do Front End SQL
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Uma implantação de servidor do Standard Edition instala automaticamente o software de banco de dados do Microsoft SQL Server Express necessárias e o banco de dados do SQL Server. Portanto, todas as opções são pré-preenchido, e você não pode fazer alterações na configuração padrão.
ms.openlocfilehash: 9a05561ac1e3c59aa8d66d6a872bc5159308f162
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21060959"
---
# <a name="add-front-end-sql-server-store"></a>Adicionar repositório de servidor do Front End SQL
 
Uma implantação de servidor do Standard Edition instala automaticamente o software de banco de dados do Microsoft SQL Server Express necessárias e o banco de dados do SQL Server. Portanto, todas as opções são pré-preenchido, e você não pode fazer alterações na configuração padrão.
  
O pool de Front-End de uma implantação do Enterprise Edition server requer uma edição de 64 bits com suporte do software de banco de dados do SQL Server para o banco de dados de back-end. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para o banco de dados de back-end, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residem e a instância do SQL S servidor que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar). Você também pode optar por habilitar o espelhamento no repositório do SQL Server e especifique a testemunha de espelhamento de failover automático.
  
Para obter detalhes sobre SQL Server suporte, consulte o [Software de banco de dados e suporte a clusters](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de suporte. Para obter detalhes sobre como configurar o SQL Server para o banco de dados de back-end, consulte [Configurar o SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) na documentação de implantação.
  
> [!NOTE]
> Se a conta que é usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de back-end (comunicação em tempo real (RTC)) quando você publica sua topologia. Também é possível criar o banco de dados mais tarde, incluindo como parte do procedimento de instalação. 
  
> [!NOTE]
> Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação do Enterprise Edition, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados. Se você não é um membro do grupo de sysadmins do SQL Server, você deverá solicitar a ser adicionado ao grupo até que os arquivos de banco de dados são implantados. Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados. Para obter detalhes sobre os direitos e permissões necessárias para realizar os procedimentos, consulte [Permissões de implantação para o SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx). 
  

