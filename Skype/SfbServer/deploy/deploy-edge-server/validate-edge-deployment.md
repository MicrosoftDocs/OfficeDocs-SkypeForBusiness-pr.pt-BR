---
title: Validar sua implantação de borda no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: Saiba como verificar se sua implantação do servidor de borda ou pool de servidor de borda está funcionando no Skype para Business Server.'
ms.openlocfilehash: 63c4cb1af599da191d0e0f4b95cfdaa775a64ba4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878603"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar sua implantação de borda no Skype para Business Server
 
**Resumo:** Saiba como verificar se sua implantação do servidor de borda ou pool de servidor de borda está funcionando no Skype para Business Server.
  
Depois que você implantou o servidor de borda ou pool de servidor de borda, você precisa saber se ela está funcionando corretamente. Aqui estão algumas coisas que possa ajudar com confirmando seu ambiente de borda está conectada por seus servidores internos e também que os usuários externos podem se conectam ao seu Skype para ambiente de servidor de negócios por meio de sua borda.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificar conectividade entre seus servidores internos e seus servidores de Borda

Enquanto a validação de conectividade é feita automaticamente no servidor de borda ou pool de servidores de borda quando os servidores de borda estão instalados, você pode confirmar isso para si mesmo ainda com o Windows PowerShell. Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tem gerenciamento Central armazenar ou qualquer computador que ingressou domínio no qual Skype para componentes de principais (ocscore. msi) do Business Server estão instaladas.
  
O resultado inicial da execução deste comando pode mostrar um status Falso, em vez de Verdadeiro, para a replicação. Caso isso ocorra, execute o cmdlet Invoke-CsManagementStoreReplication. Aguarde até ele concluir a replicação e depois execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificar conectividade de seus usuários externos

Temos uma ótima ferramenta para confirmar a configuração do servidor de borda e a capacidade de se conectar, enviar e receber as mensagens corretas para cenários de servidor de borda. É o [site de Anaylzer de conectividade remota](https://testconnectivity.microsoft.com/). Este é um site gerenciado e mantido pelo Suporte da Microsoft. Para utilizar esta ferramenta, navegue até o site e siga as instruções para escolher o cenário correto para você.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Elementos a serem levados em consideração ao testar a conectividade de usuários externos

Os testes de acesso de usuários externos devem incluir qualquer tipo de usuário interno suportado pela sua organização, incluindo qualquer um ou todos os seguintes:
  
- Usuários de pelo menos um domínio federado (porém, recomendamos testar todos).
    
- Usuários anônimos.
    
- Usuários em sua organização que estão conectados a Skype para negócios remotamente, mas não estiverem usando a VPN.
    
Esses testes determinará se o seu servidor de borda é:
  
- Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
  - Por exemplo: telnet sip.contoso.com 443
    
  - Você deve executar o teste anterior nas portas que você está usando no seu servidor de borda ou pool de servidores de borda, dependendo da sua implantação.
    
- Executa a resolução DNS externa precisa.
    
  - De fora da rede, execute ping cada um dos FQDNs externos do seu servidor de borda ou pool de servidores de borda. Mesmo se o ping falhar, você verá os endereços IP, que você possa comparar os endereços IP que você atribuiu anteriormente.
    

