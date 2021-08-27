---
title: Remover a Instância do SQL Server e os bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você remove os Microsoft SQL Server e instâncias após remover os servidores em execução que dependem deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando você retirar o SQL Server atual ou reconfigurar o servidor atual de forma que ele renderiza os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582025"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover a Instância do SQL Server e os bancos de dados no Servidor Back-End

Você remove os Microsoft SQL Server e instâncias após remover os servidores em execução que dependem deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando você retirar o SQL Server atual ou reconfigurar o servidor atual de forma que ele renderiza os bancos de dados obsoletos ou indisponíveis.
  
Para remover os bancos de dados ou instâncias do Servidor de Arquivamento ou do Servidor de Monitoramento, primeiro remova a função de servidor. Da mesma forma, para remover as instâncias ou bancos de dados do pool de Front-End, primeiro você deve remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados colocados ou instâncias separadas. Os procedimentos não são afetados pela colocação do banco de dados.
  
## <a name="in-this-section"></a>Nesta seção

- [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)
    

