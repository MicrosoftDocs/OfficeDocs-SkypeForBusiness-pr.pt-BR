---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar a replicação da preparação de domínio realizada na Etapa 1: Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio. Faça o seguinte:'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801651"
---
# <a name="verify-replication-in-the-domain"></a>Verificar a Replicação no Domínio
 
Para verificar a replicação da preparação de domínio realizada na Etapa **1:** Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio. Faça o seguinte:
  
1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**
    
2. No Windows PowerShell, digite o seguinte:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por exemplo:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas. Se suas configurações são armazenadas no contêiner Sistema (o que é comum em implantações de atualização que não tiveram a configuração global migrada para o contêiner Configuração), defina um controlador de domínio na raiz da floresta dos Serviços de Domínio Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory. 
  
    Se você não especificar o parâmetro Domínio, o valor é configurado para o domínio local. Este cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio foi bem-sucedida.
    

