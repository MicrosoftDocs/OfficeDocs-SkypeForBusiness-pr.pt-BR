---
title: Verificar a Replicação da Preparação da Floresta
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar se a replicação do Catálogo Global e a criação de objetos durante a Preparação da Floresta foi bem-sucedida, faça o seguinte:'
ms.openlocfilehash: 845a53bc466dc586b63eaf8427c3e0ba23800886
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744767"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificar a Replicação da Preparação da Floresta
 
Para confirmar se a replicação do Catálogo Global e a criação de objetos durante a Preparação da Floresta foi bem-sucedida, faça o seguinte:
  
1. Em um controlador de domínio (preferencialmente em um site remoto de outros controladores de domínio), na floresta na qual a Preparação da Floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
2. Em **Usuários e Computadores do Active Directory**, expanda o nome do domínio de sua floresta ou domínio filho.
    
3. Clique no contêiner **Usuários** no painel esquerdo e procure o grupo Universal CsAdministrator no painel direito. Se CsAdministrator (entre outros oito novos grupos Universais que começam com Cs) estiver presente, a replicação da Preparação da Floresta foi bem-sucedida.
    
4. Caso o(s) grupo(s) ainda não estejam presentes, você pode forçar a replicação ou aguardar 15 minutos e atualizar o painel do lado direito. A replicação está completa quando os grupos estiverem presentes.
    
> [!TIP]
> Se quiser revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário dos Serviços de Domínio do Active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

