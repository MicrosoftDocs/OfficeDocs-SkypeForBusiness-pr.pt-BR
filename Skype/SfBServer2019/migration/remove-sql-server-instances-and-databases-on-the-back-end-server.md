---
title: Remover instâncias do SQL Server e os bancos de dados do servidor Back-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados. Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027876"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias do SQL Server e os bancos de dados do servidor Back-End

Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados. Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.
  
Para remover os bancos de dados ou instâncias do servidor de arquivamento ou o Monitoring Server, você deve remover primeiro a função de servidor. Da mesma forma, para remover os bancos de dados para o pool de Front-End ou instâncias, você deve primeiro remover ou reconfigurar a função de servidor dependentes. Estes procedimentos não fazem nenhuma distinção entre bancos de dados colocados ou instâncias separadas para servidores. Os procedimentos são afetados pela colocação de bancos de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do SQL Server para um pool de Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover o banco de dados do SQL Server para um servidor de monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do SQL Server para um servidor de arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

