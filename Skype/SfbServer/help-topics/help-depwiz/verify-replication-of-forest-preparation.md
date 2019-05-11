---
title: Verificar a Replicação da Preparação da Floresta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que tenham a replicação do Catálogo Global e a criação de objetos durante a preparação da floresta foi bem-sucedida, faça o seguinte:'
ms.openlocfilehash: 23e3aa84cd00c68ae126991c714c35b5fdf33536
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887276"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificar a Replicação da Preparação da Floresta
 
Para confirmar que tenham a replicação do Catálogo Global e a criação de objetos durante a preparação da floresta foi bem-sucedida, faça o seguinte:
  
1. Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
2. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.
    
3. Clique no recipiente de **usuários** no painel esquerdo e procure o grupo Universal CsAdministrator no painel lateral direita. Se CsAdministrator (entre oito outros novos grupos universais que começam com Cs) estiver presente, a replicação da preparação da floresta foi bem-sucedida.
    
4. Se os grupos ainda não estiver presente, você pode forçar a replicação ou aguarde 15 minutos e atualizar o painel do lado direito. Quando os grupos estiverem presentes, a replicação será concluída.
    
> [!TIP]
> Se desejar examinar os arquivos de log são criados pelo Skype para o Assistente de implantação do Business Server, você pode encontrá-los no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário Active Directory Domain Services que executou a etapa. Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

