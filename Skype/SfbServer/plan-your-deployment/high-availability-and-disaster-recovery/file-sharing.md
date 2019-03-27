---
title: Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Saiba mais sobre a garantir a alta disponibilidade de seus compartilhamentos de arquivo no Skype para Business Server, o uso do DFS.
ms.openlocfilehash: 0b5d2f577775635b95add15dd7b7576ca24c883f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894206"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server
 
Saiba mais sobre a garantir a alta disponibilidade de seus compartilhamentos de arquivo no Skype para Business Server, o uso do DFS.
  
Para garantir a alta disponibilidade para o compartilhamento de arquivo no seu Skype para implantação de servidor de negócios, você pode usar o sistema de arquivos distribuídos (DFS). O DFS suporta failover de um servidor de arquivos para outro dentro do mesmo data center. Para uma implantação de larga escala, recomendamos usar servidores de arquivos dedicados, emparelhados com o uso do DFS. Para obter mais informações sobre o DFS no Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Para obter informações sobre o DFS no Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Dependendo do tamanho da sua rede e a quantidade de resiliência desejado, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou use um par por pool de Front-End.
  
O DFSS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO). Um failover entre servidores DFS deve ser concluído rapidamente, mas o atraso de replicação de dados pode impedir que os usuários consigam continuar o trabalho em andamento quando ocorre o failover.
  
Se você usa o DFS e o armazenamento de dados no compartilhamento de arquivos for importante, você deve efetuar o backup de compartilhamentos de arquivos frequentemente, como a cada 4 a 8 horas. Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.
  

