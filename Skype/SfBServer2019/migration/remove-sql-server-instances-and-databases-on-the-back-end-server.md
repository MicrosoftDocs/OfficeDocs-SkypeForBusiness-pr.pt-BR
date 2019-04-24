---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados. Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231501"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias SQL Server e bancos de dados no Servidor Back-End

Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados. Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.
  
Para remover os bancos de dados ou instâncias do servidor de arquivamento ou o Monitoring Server, você deve remover primeiro a função de servidor. Da mesma forma, para remover os bancos de dados para o pool de Front-End ou instâncias, você deve primeiro remover ou reconfigurar a função de servidor dependentes. Estes procedimentos não fazem nenhuma distinção entre bancos de dados colocados ou instâncias separadas para servidores. Os procedimentos são afetados pela colocação de bancos de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

