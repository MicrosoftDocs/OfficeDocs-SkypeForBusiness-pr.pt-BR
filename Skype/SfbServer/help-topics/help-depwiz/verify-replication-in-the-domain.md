---
title: Verificar Replicação no Domínio
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Para verificar a replicação a preparação do domínio realizada na etapa 1: preparar esquema, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio. Faça o seguinte:'
ms.openlocfilehash: b6d16189804bfef18db8aa1063fe95257f782f54
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373768"
---
# <a name="verify-replication-in-the-domain"></a>Verificar Replicação no Domínio
 
Para verificar a replicação sobre a preparação de domínio realizada no **etapa 1: preparar esquema**, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio. Faça o seguinte:
  
1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. No Windows PowerShell, digite o seguinte:
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por exemplo:
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais estão armazenadas. Se as configurações são armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração de global migrados para o contêiner configuração), você define um controlador de domínio na raiz da floresta do Active Directory Domain Services. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory. 
  
    Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local. Este cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio foi bem-sucedida.
    

