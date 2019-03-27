---
title: Remover um pool Front-End ou um servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico o orienta o processo de remoção de um pool de Front-End ou um Standard Edition servidor Front-End. Quando você remover um pool de Front-End, você pode remover cada servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Quando você remove um Standard Edition servidor Front-End, você deve remover a definição de repositório SQL do construtor de topologia.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872714"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover um pool Front-End ou um servidor Standard Edition

Este artigo o orienta o processo de remoção de um pool de Front-End ou um Standard Edition servidor Front-End. Quando você remover um pool de Front-End, você pode remover cada servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Quando você remove um Standard Edition servidor Front-End, você deve remover a definição de repositório SQL do construtor de topologia.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para remover um pool de servidor Front-End

1. Abra o construtor de topologia.
    
2. Navegue até o nó herdado.
    
3. Expanda **pools de Front End do Enterprise Edition**, expanda o pool de Front-End, com o botão direito do pool de Front-End que você deseja remover e clique em **Excluir**.
    
4. Publique a topologia, verifique o status de replicação e execute o Assistente de implantação herdadas conforme necessário. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para remover um servidor de Front End e Standard Edition

1. Abra o construtor de topologia.
    
2. Navegue até o nó de instalações herdadas.
    
3. Expanda **servidores Standard Edition Front-End**, com o botão direito do servidor Front-End que você deseja remover e clique em **Excluir**.
    
4. Expanda **SQL armazena**, clique com o botão o banco de dados do SQL Server que está associado a Standard Edition servidor Front-End e, em seguida, clique em **Excluir**.
    
    > [!IMPORTANT]
    > Você deve remover a definição dos bancos de dados do SQL Server colocados do Standard Edition servidor Front-End. 
  
5. Publique a topologia, verifique o status de replicação e, em seguida, execute o Assistente para implantação, conforme necessário. 
    

