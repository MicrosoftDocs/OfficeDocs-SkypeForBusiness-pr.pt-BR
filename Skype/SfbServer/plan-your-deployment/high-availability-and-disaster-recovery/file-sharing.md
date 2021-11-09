---
title: Alta disponibilidade de compartilhamento de arquivos Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Saiba mais sobre como garantir alta disponibilidade de seus compartilhamentos de arquivos Skype for Business Server, usando DFS.
ms.openlocfilehash: e0af97da0bfc5a6ddb07284943640511e0dc06ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859868"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Alta disponibilidade de compartilhamento de arquivos Skype for Business Server
 
Saiba mais sobre como garantir alta disponibilidade de seus compartilhamentos de arquivos Skype for Business Server, usando DFS.
  
Para garantir alta disponibilidade para compartilhamento de arquivos em sua implantação Skype for Business Server, você pode usar o DFS (Sistema de Arquivos Distribuídos). O DAS oferece suporte a failover de um servidor de arquivos para outro no mesmo data Center. Para uma implantação em grande escala, nós recomendamos que você use servidores de arquivos dedicados emparelhados usando DAS. Para obter mais informações sobre o DFS Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) . Para obter informações sobre o DFS no Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .
  
Dependendo do tamanho da rede e da quantidade de resiliência desejada, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou usar um par por pool de front-end.
  
O DAS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO). Um failover entre servidores DFS deve ser concluído rapidamente, mas o atraso na replicação de dados pode impedir que os usuários possam continuar a trabalhar em andamento quando o failover acontece.
  
Se você usar o DFS e o armazenamento de dados no compartilhamento de arquivos for fundamental, você deve fazer o back up dos compartilhamentos de arquivos com frequência, como a cada 4 a 8 horas. Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.
