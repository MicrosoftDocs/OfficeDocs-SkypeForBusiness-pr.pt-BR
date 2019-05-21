---
title: Gerenciar bancos de dados com um grupo de disponibilidade AlwaysOn no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: saiba como adicionar mais bancos de dados do Skype for Business Server a um grupo de disponibilidade AlwaysOn existente e saber mais sobre as etapas adicionais necessárias após o patch ou a atualização de um servidor back-end que faz parte de um grupo de disponibilidade AlwaysOn no Skype para Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275182"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gerenciar bancos de dados com um grupo de disponibilidade AlwaysOn no Skype for Business Server

Use as etapas neste artigo para adicionar mais bancos de dados do Skype for Business Server a um grupo de disponibilidade AlwaysOn existente no Skype for Business Server e saber mais sobre as etapas adicionais necessárias após o patch ou a atualização de um servidor back-end que faz parte de um AlwaysOn Grupo de disponibilidade no Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Adicionar bancos de dados a um grupo de disponibilidade AlwaysOn 

1. Abra o SQL Server Management Studio e navegue até o grupo disponibilidade AlwaysOn. Fazer failover para a réplica primária.
    
2. Em Construtor de topologia, defina o FQDN do SQL Server do grupo de disponibilidade AlwaysOn para o FQDN do nó primário do grupo.
    
   - Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão direito do mouse no repositório SQL do novo grupo de disponibilidade AlwaysOn e clique em **Editar propriedades**.
    
   - Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó primário do grupo de disponibilidade AlwaysOn.
    
3. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
4. Use o SQL Server Management Studio para adicionar o novo banco de dados ao grupo de disponibilidade AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn

Depois de corrigir um servidor back-end que faz parte de um grupo de disponibilidade AlwaysOn, você deve republicar a topologia.

1. Instale a atualização em um ou vários servidores do Skype for Business.
    
2. Execute o seguinte comando do PowerShell no Skype for Business Management Shell (acessado com uma conta que tenha a devida permissão para aplicar alterações nos bancos de dados do SQL AlwaysOn) conforme segue:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Quando o [sqlpool.contoso.com] é substituído pelo FQDN (Nome do domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.
