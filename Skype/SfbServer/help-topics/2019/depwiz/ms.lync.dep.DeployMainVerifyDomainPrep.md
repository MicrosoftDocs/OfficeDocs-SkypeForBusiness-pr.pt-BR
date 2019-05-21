---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar a replicação da preparação do domínio realizada na etapa 1: preparar o esquema, é necessário executar um cmdlet do Shell de gerenciamento do Shell de gerenciamento do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Domain admins. Do the following:'
ms.openlocfilehash: 0b853a071116525ad313cf351685124bf92782a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303351"
---
# <a name="verify-replication-in-the-domain"></a>Verificar Replicação no Domínio
 
Para verificar a replicação da preparação do domínio realizada na **etapa 1: preparar o esquema**, é necessário executar um cmdlet do Shell de gerenciamento do Shell de gerenciamento do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Domain admins. Do the following:
  
1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
2. No Windows PowerShell, digite o seguinte:
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por exemplo:
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais estão armazenadas. Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração global migrada para o contêiner de configuração), defina um controlador de domínio na raiz da floresta dos serviços de domínio Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory. 
  
    Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local. Esse cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio tiver êxito.
    

