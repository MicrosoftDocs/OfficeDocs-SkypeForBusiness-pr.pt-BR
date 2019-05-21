---
title: Verificar a Replicação da Preparação da Floresta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para confirmar se a replicação do catálogo global e a criação de objetos durante a preparação da floresta foram bem-sucedidas, faça o seguinte:'
ms.openlocfilehash: c7fe425dcbecf2bfba02d4862bc3a29b75e16910
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303338"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificar a Replicação da Preparação da Floresta
 
Para confirmar se a replicação do catálogo global e a criação de objetos durante a preparação da floresta foram bem-sucedidas, faça o seguinte:
  
1. Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
2. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.
    
3. Clique no contêiner **usuários** no painel esquerdo e procure o grupo universal CsAdministrator no painel do lado direito. Se CsAdministrator (entre oito outros novos grupos universais que comecem com o CS) estiver presente, a replicação da preparação da floresta foi bem-sucedida.
    
4. Se o (s) grupo (s) ainda não estiver presente, você pode forçar a replicação ou aguardar 15 minutos e atualizar o painel do lado direito. Quando os grupos estiverem presentes, a replicação será concluída.
    
> [!TIP]
> Se desejar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá encontrá-los no computador em que o assistente de implantação foi executado, no diretório usuários do usuário dos serviços de domínio Active Directory que executou a etapa. Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

