---
title: Compartilhamento de arquivos com alta disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Saiba como garantir alta disponibilidade de seus compartilhamentos de arquivos no Skype for Business Server usando o DFS.
ms.openlocfilehash: 56a6e1008935bc0d38d65e2355826634709aed27
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297474"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Compartilhamento de arquivos com alta disponibilidade no Skype for Business Server
 
Saiba como garantir alta disponibilidade de seus compartilhamentos de arquivos no Skype for Business Server usando o DFS.
  
Para garantir alta disponibilidade para o compartilhamento de arquivos na implantação do Skype for Business Server, você pode usar o sistema de arquivos distribuídos (DFS). O DFS suporta failover de um servidor de arquivos para outro dentro do mesmo data center. Para uma implantação de larga escala, recomendamos usar servidores de arquivos dedicados, emparelhados com o uso do DFS. Para obter mais informações sobre o DFS no Windows Server 2012 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384), consulte. Para obter informações sobre o DFS no Windows Server 2008 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385), consulte.
  
Dependendo do tamanho da sua rede e da quantidade de resiliência desejada, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou usar um par por pool de front-end.
  
O DFSS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO). Um failover entre servidores DFS deve ser concluído rapidamente, mas o atraso da replicação de dados pode impedir que os usuários possam continuar trabalhando em andamento quando o failover ocorrer.
  
Se você usa o DFS e o armazenamento de dados no compartilhamento de arquivos for importante, você deve efetuar o backup de compartilhamentos de arquivos frequentemente, como a cada 4 a 8 horas. Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.
  

