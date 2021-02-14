---
title: Implantar bypass de mídia no Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber mais sobre as etapas para implantar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359307"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implantar bypass de mídia no Cloud Connector Edition
 
> [!Important]
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização atualizou para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Leia este tópico para saber mais sobre as etapas para implantar o bypass de mídia com o Cloud Connector Edition versão 2.0 e posterior. 
  
O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (Rede Telefônica Pública Comucionária), um gateway ou Controlador de Borda de Sessão (SBC) e elimine o componente do Cloud Connector Edition do caminho de mídia. Consulte também [Planejar o bypass de mídia no Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>Habilitar bypass de mídia

Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web de bypass de mídia e ativar o bypass de mídia na configuração do locatário. O serviço Web de bypass de mídia é implantado automaticamente em cada Servidor de Mediação. Um administrador de locatários deve escolher um nome para um serviço de voz híbrido (site), e esse nome deve ser de um domínio SIP registrado para voz híbrida. O nome do serviço deve ser o mesmo em todos os dispositivos do Cloud Connector e em todos os sites PSTN, independentemente do local do cliente. O serviço Web só deve estar disponível internamente na rede.
  
Um administrador de locatários deve configurar um registro DNS A no Active Directory de produção interna. Se você tiver um ambiente complexo de vários sites, consulte o exemplo em Exemplo: registros DNS do site de bypass de mídia em [ambientes complexos de vários sites.](deploy-media-bypass-in-cloud-connector.md#Example) O registro DNS só deve ser resolvido para clientes de rede interna; ele não deve ser resolvido para clientes de rede externa.
  
Depois de configurar o DNS, conecte-se ao Skype for Business Online usando o PowerShell remoto com credenciais de Administrador do Skype for Business. Para obter mais informações, [consulte Configurar seu computador para o Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

A habilitação do bypass de mídia é um processo de duas etapas. O New-CsNetworkMedia cmdlet não salva imediatamente a nova configuração; ele só cria as configurações na memória. O objeto criado por esse cmdlet deve ser salvo em uma variável e, em seguida, atribuído à propriedade MediaBypassSettings da configuração de rede. Para obter mais informações, consulte Exemplo: registros DNS do site de [bypass de mídia em ambientes complexos de vários sites.](deploy-media-bypass-in-cloud-connector.md#Example)
  
A replicação entre os componentes locais e online pode levar até 24 horas, portanto, a Microsoft recomenda que você execute os comandos necessários antes de habilenciar os usuários.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar configurações de bypass de mídia

Você pode verificar as configurações de bypass de mídia da seguinte forma. 
  
Para verificar a replicação online no pool de locatários, execute o seguinte comando no PowerShell remoto:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Para verificar a replicação local, conecte-se aos servidores de Mediação do Cloud Connector, execute o seguinte comando no PowerShell e confirme se Enabled=True e AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Para verificar as configurações do cliente, saia do cliente Skype for Business, entre novamente e confirme se o cliente recebeu a URL de serviço da seguinte forma:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Pesquise hybridconfigserviceinternalurl e confirme se a URL corresponde à que você definiu.
    
## <a name="change-media-bypass-parameters"></a>Alterar parâmetros de bypass de mídia

Os administradores de locatários podem alterar o nome DNS do serviço Web executando o seguinte cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Os clientes precisam sair e entrar para obter o novo nome de serviço e reconhecer a alteração. 
  
## <a name="temporarily-disable-media-bypass"></a>Desabilitar temporariamente o bypass de mídia

Esse cenário pode ser útil para solução de problemas ou manutenção. Para desabilitar o serviço, execute os seguintes cmdlets:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Depois de fazer a alteração, pode levar algum tempo para que as alterações se repliquem em todos os Cloud Connectors. Para verificar o status da replicação, execute o seguinte cmdlet no PowerShell nos servidores de Mediação do Cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Depois que as alterações replicarem, o serviço Web no Servidor de Mediação começará a rejeitar solicitações de cliente para o serviço de bypass de mídia.
  
## <a name="disable-media-bypass-permanently"></a>Desabilitar o bypass de mídia permanentemente

Para desabilitar permanentemente o bypass de mídia, um administrador de locatários precisa executar os seguintes comandos: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Um administrador também precisará remover os endereços da Web para bypass de mídia de servidores DNS internos. Depois de fazer a alteração, pode levar algum tempo para que as alterações se repliquem em todos os dispositivos do Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemplo: registros DNS do site de bypass de mídia em ambientes complexos de vários sites
<a name="Example"> </a>

Os clientes receberão o endereço Web do serviço Web de bypass de mídia de um servidor DNS interno. O nome do serviço Web será o mesmo em todos os dispositivos do Cloud Connector e sites PSTN do Cloud Connector. Em um ambiente complexo de vários sites, recomendamos usar a Política DNS do Windows 2016 para gerenciamento de tráfego baseado em Geo-Location, para que os clientes possam ser redirecionados para o serviço Web local para sua rede. 
  
Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
A seguir está um exemplo de configuração para uma empresa com vários sites usando a Política DNS do Windows 2016 para gerenciamento de tráfego Geo-Location baseado em segurança.
  
O nome do serviço de bypass é 'hybridvoice.adatum.biz'.
  
O site em Amsterdã tem quatro dispositivos do Cloud Connector implantados com os seguintes endereços IP do Servidor de Mediação:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
O site em Seattle tem três dispositivos do Cloud Connector implantados com os seguintes endereços IP do Servidor de Mediação:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Usando Geo-Location Gerenciamento de Tráfego Baseado em Função, os servidores DNS seriam configurados da seguinte forma:
  
1. Crie sub-redes de cliente DNS para as sub-redes de Amsterdã e Seattle.
    
2. Crie escopos de zona DNS para adatum.biz para Amsterdã e Seattle.
    
3. Crie registros DNS em cada escopo de zona DNS.
    
    Amsterdã
    
   - Tipo A;
    
   - Nome : hybridvoice na adatum.biz DNS
    
   - Destino: 192.168.1.45
    
     Criar registros adicionais para servidores de mediação adicionais
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tipo A
    
   - Nome : hybridvoice na adatum.biz DNS
    
   - Destino: 10.10.1.8
    
     Criar registros adicionais para servidores de mediação adicionais
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Crie a política DNS que conecta as sub-redes do cliente aos escopos de zona apropriados para garantir a resolução de DNS desejada.
    
Neste ponto, os clientes que fazem consultas DNS da sub-rede de Amsterdã hybridvoice.adatum.biz retornarão a 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, enquanto os clientes que criarem o mesmo formulário de consulta Seattle retornarão 10.10.1.8, 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se o dispositivo CCE não parece estar recebendo as configurações atualizadas, verifique se o dispositivo é capaz de entrar em contato com o locatário por meio do PowerShell remoto. Você pode usar o PowerShell Remoto para verificar o status do dispositivo com Get-CsHybridPSTNAppliance ou usar o PowerShell no host CCE para verificar o status com Get-CcApplianceStatus.

  
## <a name="see-also"></a>Confira também
<a name="Example"> </a>

[Plano para bypass de mídia no Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
