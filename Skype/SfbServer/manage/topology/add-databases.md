---
title: Adicionar bancos de dados a um grupo de disponibilidade do AlwaysOn no Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Adicionar bancos de dados a um grupo de disponibilidade do AlwaysOn no Skype para Business Server 2015
 
**Resumo:** Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server 2015.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Adicionar bancos de dados para um grupo de disponibilidade do AlwaysOn

1. Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn. Failover para a réplica primária.
    
2. No construtor de topologia, defina o FQDN do grupo de disponibilidade do AlwaysOn do SQL Server para o FQDN do nó principal desse grupo.
    
  - Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.
    
  - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.
    
  - Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn.
    
3. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**.
    
4. Use o SQL Server Management Studio para adicionar o novo banco de dados para o grupo de disponibilidade do AlwaysOn.
    

