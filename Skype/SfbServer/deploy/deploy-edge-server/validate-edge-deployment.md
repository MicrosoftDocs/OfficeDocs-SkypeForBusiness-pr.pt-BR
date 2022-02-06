---
title: Validar sua implantação de Borda no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: saiba como verificar se a implantação do Servidor de Borda ou pool do Servidor de Borda está funcionando Skype for Business Server.'
---

# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Validar sua implantação de Borda no Skype for Business Server
 
**Resumo:** Saiba como verificar se a implantação do Servidor de Borda ou pool do Servidor de Borda está funcionando Skype for Business Server.
  
Depois de ter implantado seu pool de Servidor de Borda ou Servidor de Borda, você precisa saber se ele está funcionando corretamente. Aqui estão algumas coisas que podem ajudar na confirmação de que seu ambiente de Borda está conectado aos servidores internos e também que os usuários externos podem se conectar ao seu ambiente Skype for Business Server por meio do Edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Verificar a conectividade entre seus servidores internos e seus servidores de Borda

Embora a validação da conectividade seja feita automaticamente no pool do Servidor de Borda ou do Servidor de Borda quando os Servidores de Borda estão instalados, você ainda pode confirmar isso por conta própria com Windows PowerShell. Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tenha o armazenamento de Gerenciamento Central ou qualquer computador ingressado no domínio no qual Skype for Business Server Componentes Principais (OcsCore.msi) estão instalados.
  
O resultado inicial da execução desse comando pode dar um status False, em vez de True, para replicação. Se isso acontecer, execute o Invoke-CsManagementStoreReplication cmdlet. Dê algum tempo para concluir a replicação e, em seguida, execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.
  
## <a name="verify-connectivity-for-your-external-users"></a>Verificar a conectividade para seus usuários externos

Temos uma ótima ferramenta para confirmar sua configuração do Servidor de Borda e a capacidade de conectar, enviar e receber as mensagens corretas para cenários do Servidor de Borda. É o site [do Anaylzer conectividade remota](https://testconnectivity.microsoft.com/). Este é um site gerenciado e mantido pelo Suporte da Microsoft. Para usar essa ferramenta, navegue até o site e siga as instruções para escolher o cenário certo para você.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Coisas a considerar ao testar a conectividade do usuário externo

Qualquer teste para acesso de usuário externo precisa incluir cada tipo de usuário interno compatível com sua organização, o que pode incluir qualquer um dos seguintes:
  
- Usuários de pelo menos um domínio federado (recomendamos testá-los a todos).
    
- Usuários anônimos.
    
- Usuários em sua organização que estão conectados Skype for Business remotamente, mas não estão usando VPN.
    
Esses testes determinarão se o Servidor de Borda é:
  
- Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
  - Por exemplo: telnet sip.contoso.com 443
    
  - Você deve executar o teste anterior nas portas que você está usando no pool do Servidor de Borda ou do Servidor de Borda, dependendo da implantação.
    
- Executa a resolução DNS externa precisa.
    
  - De fora da rede, ping cada um dos FQDNs externos do seu servidor de borda ou pool de Servidor de Borda. Mesmo que o ping falhe, você verá os endereços IP, que podem ser comparados aos endereços IP atribuídos anteriormente.
    

