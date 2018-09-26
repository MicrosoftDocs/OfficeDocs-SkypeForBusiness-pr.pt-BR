---
title: Remover o pool de Front-End ou servidor Standard Edition
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico o orienta o processo de remoção de um pool de Front-End ou um Standard Edition servidor Front-End. Quando você remover um pool de Front-End, você pode remover cada servidor Front-End que pertence ao pool como parte do processo de remoção do pool. Quando você remove um Standard Edition servidor Front-End, você deve remover a definição de repositório SQL do construtor de topologia.
ms.openlocfilehash: 7e56f2e9ff57536d1f065452f299a9af33a46aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028884"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Remover o pool de Front-End ou servidor Standard Edition

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
    

