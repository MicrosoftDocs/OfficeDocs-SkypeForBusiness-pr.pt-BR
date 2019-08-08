---
title: Validar a implantação do seu Edge no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: saiba como verificar se sua implantação do servidor de borda ou do pool do servidor de borda está funcionando no Skype for Business Server.'
ms.openlocfilehash: 57994e4583a3424fc680c8dfb220aeb11668c6fc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233871"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar a implantação do seu Edge no Skype for Business Server
 
**Resumo:** Saiba como verificar se sua implantação do servidor de borda ou do pool do servidor de borda está funcionando no Skype for Business Server.
  
Depois de implantar o servidor de borda ou o pool do servidor de borda, você precisa saber se ele está funcionando corretamente. Veja a seguir algumas coisas que podem ajudar a confirmar se o ambiente de borda está conectado a seus servidores internos e também que seus usuários externos podem se conectar ao ambiente do Skype for Business Server por meio de sua borda.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificar conectividade entre seus servidores internos e seus servidores de Borda

Enquanto a validação de conectividade é feita automaticamente no servidor de borda ou no pool do servidor de borda quando os servidores de borda são instalados, você ainda pode confirmar isso por conta própria com o Windows PowerShell. Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tem o repositório de gerenciamento central ou qualquer computador associado a domínio no qual os componentes principais do Skype for Business Server (OcsCore. msi) estão instalados.
  
O resultado inicial da execução deste comando pode mostrar um status Falso, em vez de Verdadeiro, para a replicação. Caso isso ocorra, execute o cmdlet Invoke-CsManagementStoreReplication. Aguarde até ele concluir a replicação e depois execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificar conectividade de seus usuários externos

Temos uma ótima ferramenta para confirmar a configuração do servidor de borda e a capacidade de se conectar, enviar e receber as mensagens corretas para cenários do servidor de borda. É o [site de Anaylzer de conectividade remota](https://testconnectivity.microsoft.com/). Este é um site gerenciado e mantido pelo Suporte da Microsoft. Para utilizar esta ferramenta, navegue até o site e siga as instruções para escolher o cenário correto para você.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Elementos a serem levados em consideração ao testar a conectividade de usuários externos

Os testes de acesso de usuários externos devem incluir qualquer tipo de usuário interno suportado pela sua organização, incluindo qualquer um ou todos os seguintes:
  
- Usuários de pelo menos um domínio federado (porém, recomendamos testar todos).
    
- Usuários anônimos.
    
- Os usuários em sua organização que estão conectados ao Skype for Business remotamente, mas não estão usando a VPN.
    
Esses testes determinarão se o servidor de borda é:
  
- Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
  - Por exemplo: telnet sip.contoso.com 443
    
  - Você deve executar o teste anterior nas portas que você está usando em seu servidor de borda ou em um pool de servidor de borda, dependendo da sua implantação.
    
- Executa a resolução DNS externa precisa.
    
  - De fora da sua rede, execute ping em cada um dos FQDNs externos do seu servidor de borda ou de um pool de servidor de borda. Mesmo que o ping falhe, você verá os endereços IP, para os quais você pode comparar os endereços IP que você atribuiu anteriormente.
    

