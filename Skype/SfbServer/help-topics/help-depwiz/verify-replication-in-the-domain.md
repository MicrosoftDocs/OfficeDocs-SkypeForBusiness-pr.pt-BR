---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Para verificar a replicação da preparação de domínio realizada na Etapa 1: Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server Management Shell. Para executar o cmdlet Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio. Faça o seguinte:'
ms.openlocfilehash: e02708e7b995c2f83e82080be60caa1e251f6b9438a75d93c7d74f47d812db93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319274"
---
# <a name="verify-replication-in-the-domain"></a>Verificar a Replicação no Domínio
 
Para verificar a replicação da preparação de domínio realizada na Etapa **1:** Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server Management Shell. Para executar o cmdlet Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio. Faça o seguinte:
  
1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Em Windows PowerShell, digite o seguinte:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Por exemplo:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas. Se suas configurações são armazenadas no contêiner Sistema (o que é típico de implantações de atualização que não tiveram a configuração global migrada para o contêiner de Configuração), você define um controlador de domínio na raiz da floresta dos Serviços de Domínio do Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner De configuração e se referirá a qualquer controlador de domínio no Active Directory. 
  
    Se você não especificar o parâmetro Domínio, o valor é configurado para o domínio local. Este cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio foi bem-sucedida.
    

