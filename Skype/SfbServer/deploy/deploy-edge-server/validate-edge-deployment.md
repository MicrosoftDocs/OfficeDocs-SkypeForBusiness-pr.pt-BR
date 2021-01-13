---
title: Validar sua implantação de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: Saiba como verificar se a implantação do Servidor de Borda ou pool de Servidores de Borda está funcionando no Skype for Business Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804351"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar sua implantação de Borda no Skype for Business Server
 
**Resumo:** Saiba como verificar se a implantação do Servidor de Borda ou pool de Servidores de Borda está funcionando no Skype for Business Server.
  
Depois de ter implantado seu Servidor de Borda ou pool de Servidores de Borda, você precisará saber se ele está funcionando corretamente. Aqui estão algumas coisas que podem ajudar na confirmação de que seu ambiente de Borda está conectado aos seus servidores internos e também que seus usuários externos podem se conectar ao seu ambiente do Skype for Business Server por meio de sua Borda.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificar a conectividade entre os servidores internos e os servidores de Borda

Embora a validação da conectividade seja feita automaticamente no Servidor de Borda ou no pool do Servidor de Borda quando os Servidores de Borda são instalados, você ainda pode confirmar isso por conta própria com o Windows PowerShell. Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tem o armazenamento de Gerenciamento Central ou em qualquer computador ingressado no domínio no qual os Componentes Principais do Skype for Business Server (OcsCore.msi) estão instalados.
  
O resultado inicial da execução deste comando pode dar um status False, em vez de True, para replicação. Se isso acontecer, execute o Invoke-CsManagementStoreReplication cmdlet. Dê algum tempo para concluir a replicação e execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificar a conectividade de seus usuários externos

Temos uma ótima ferramenta para confirmar sua configuração do Servidor de Borda e a capacidade de se conectar, enviar e receber as mensagens corretas para cenários do Servidor de Borda. É o site [De análogo de Conectividade Remota.](https://testconnectivity.microsoft.com/) Este é um site gerenciado e mantido pelo Suporte da Microsoft. Para usar essa ferramenta, navegue até o site e siga as instruções para escolher o cenário certo para você.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Itens a considerar ao testar a conectividade do usuário externo

Qualquer teste de acesso de usuário externo precisa incluir cada tipo de usuário interno compatível com sua organização, o que pode incluir qualquer um ou todos os seguintes:
  
- Os usuários de pelo menos um domínio federado (recomendamos testá-los todos).
    
- Usuários anônimos.
    
- Usuários em sua organização que estão conectados ao Skype for Business remotamente, mas não estão usando VPN.
    
Esses testes determinarão se o Servidor de Borda é:
  
- Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
  - Por exemplo: telnet sip.contoso.com 443
    
  - Você deve realizar o teste anterior nas portas que está usando no seu Servidor de Borda ou pool de Servidores de Borda, dependendo da sua implantação.
    
- Executa a resolução DNS externa precisa.
    
  - De fora da rede, ping em cada um dos FQDNs externos do seu Servidor de Borda ou pool de Servidores de Borda. Mesmo que o ping falhe, você verá os endereços IP, que podem ser comparados aos endereços IP atribuídos anteriormente.
    

