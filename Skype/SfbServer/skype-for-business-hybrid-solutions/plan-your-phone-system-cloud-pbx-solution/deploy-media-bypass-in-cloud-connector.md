---
title: Implantar o bypass de mídia no Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber mais sobre as etapas de implantação do bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior.
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287542"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implantar o bypass de mídia no Cloud Connector Edition
 
Leia este tópico para saber mais sobre as etapas de implantação do bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior. 
  
O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da rede telefônica pública comutada (PSTN), um gateway ou um controlador de borda de sessão (SBC), e elimine o componente da edição do conector de nuvem do caminho de mídia. Consulte também [planejar a bypass de mídia na edição do Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar bypass de mídia

Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web do bypass de mídia e ativar o bypass de mídia na configuração do locatário. O serviço Web de bypass de mídia é implantado automaticamente em cada Servidor de Mediação. Um administrador de locatário precisa escolher um nome para um serviço de voz híbrido (site), e esse nome deve ser de um domínio SIP registrado para voz híbrida. O nome do serviço deve ser o mesmo em todos os dispositivos de conector de nuvem e em todos os sites PSTN, independentemente do local do cliente. O serviço Web só deve estar disponível internamente na rede.
  
O administrador do locatário deve configurar um registro A DNS no Active Directory da produção interna. Se você tiver um ambiente de vários sites complexo, consulte o exemplo no exemplo [: ignorar o site do Web site registros DNS em ambientes com vários sites complexos](deploy-media-bypass-in-cloud-connector.md#Example). O registro DNS deve resolver apenas clientes da rede interna; ele não deve resolver clientes da rede externa.
  
Depois de configurar o DNS, conecte-se ao Skype for Business Online usando o PowerShell remoto com as credenciais de administrador do Skype for Business. Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Habilitando o bypass de mídia em um processo de duas etapas. O cmdlet New-CsNetworkMedia não salva imediatamente a nova configuração; ele só cria as configurações na memória. O objeto criado por este cmdlet deve ser salvo como uma variável, e então atribuído à propriedade MediaBypassSettings da configuração da rede. Para obter mais informações, consulte [exemplo: ignorar a mídia de registros DNS de sites em ambientes complexos de vários locais](deploy-media-bypass-in-cloud-connector.md#Example).
  
A replicação entre os componentes locais e online pode demorar até 24 horas, portanto a Microsoft recomenda que você execute os comandos necessários antes de habilitar os usuários.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar as configurações de bypass de mídia

Você pode verificar as configurações de bypass de mídia da seguinte maneira.  
  
Para verificar a replicação online para o pool do locatário, execute o seguinte comando no PowerShell remoto:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Para verificar a replicação local, conecte-se aos servidores de remediação do conector de nuvem, execute o seguinte comando no PowerShell e confirme se Enabled = true e AlwaysBypass = true
  
```
Get-CsNetworkConfiguration -LocalStore
```

Para verificar as configurações do cliente, desconecte-se do cliente Skype for Business, entre novamente e confirme se o cliente recebeu a URL do serviço da seguinte maneira:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Procure por hybridconfigserviceinternalurl e confirme se a URL corresponde à que você definiu.
    
## <a name="change-media-bypass-parameters"></a>Alterar parâmetros de bypass de mídia

Os administradores de locatários podem alterar o nome DNS do serviço Web executando o seguinte cmdlet:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Os clientes precisam sair e entrar novamente para obter o novo nome do serviço e reconhecer a mudança.  
  
## <a name="temporarily-disable-media-bypass"></a>Desabilitar o bypass de mídia temporariamente

Esse cenário pode ser útil para a solução de problemas ou para a manutenção. Para desabilitar o serviço, execute os seguintes cmdlets:
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Depois de fazer a alteração, pode levar algum tempo até que as alterações sejam replicadas em todos os Cloud Connectors. Para verificar o status da replicação, execute o seguinte cmdlet no PowerShell em servidores de Media Connector: 
  
```
Get- CsNetworkConfiguration -LocalStore
```

Depois de replicadas as alterações, o serviço Web no Servidor de Mediação começará a rejeitar solicitações de cliente para o serviço de bypass de mídia.
  
## <a name="disable-media-bypass-permanently"></a>Desabilitar o bypass de mídia permanentemente

Para a desabilitação permanente do bypass de mídia, um administrador de locatários precisa executar os seguintes comandos: 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

O administrador também precisará remover os endereços da web para o bypass de mídia dos servidores DNS internos. Depois de fazer a alteração, pode levar algum tempo para que as alterações sejam replicadas para todos os aparelhos de conector de nuvem. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemplo: registros DNS do site de bypass de mídia em ambientes complexos multissites.
<a name="Example"> </a>

Os clientes receberão o endereço web do serviço de bypass de mídia de um servidor DNS interno. O nome do serviço Web será o mesmo em todos os dispositivos de conector de nuvem e sites PSTN do conector de nuvem. Em um ambiente complexo multissites, recomendamos usar a política de DNS do Windows 2016 para localização geográfica com base em gerenciamento de tráfego para que os clientes possam ser redirecionados para o serviço Web que seja local para a sua rede. 
  
Para saber mais sobre as políticas de DNS do Windows 2016, consulte [usar a política DNS para gerenciamento de tráfego baseado em localização geográfica com servidores primários](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Veja a seguir um exemplo de configuração para uma empresa com vários sites usando a Política DNS do Windows 2016 para Localização geográfica com base em gerenciamento de tráfego.
  
O nome do serviço de bypass é ' hybridvoice.adatum.biz '.
  
O site em Amsterdã tem quatro dispositivos de conector de nuvem implantados com os seguintes endereços IP do servidor de mediação:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
O site em Seattle tem três dispositivos de conector de nuvem implantados com os seguintes endereços IP do servidor de mediação:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Usando-se a Localização geográfica com base em gerenciamento de tráfego, os servidores DNS seriam configurados da seguinte maneira:
  
1. Crie sub-redes de cliente DNS para ambas as sub-redes de Amsterdã e de Seattle.
    
2. Crie escopos de zona DNS para adatum.biz tanto para Amsterdã quanto para Seattle.
    
3. Crie registros DNS em cada escopo de zona DNS.
    
    Amsterdã
    
   - Tipo A;
    
   - Nome : hybridvoice na zona DNS de adatum.biz
    
   - Destino: 192.168.1.45
    
     Crie registros adicionais para servidores de mediação adicionais
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Tipo A
    
   - Nome : hybridvoice na zona DNS de adatum.biz
    
   - Destino: 10.10.1.8
    
     Crie registros adicionais para servidores de mediação adicionais
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Crie a política DNS que conecta as sub-redes do cliente aos escopos de zona apropriados para garantir a resolução de DNS desejada.
    
Neste ponto, os clientes que fizerem consultas DNS da sub-rede de Amsterdã para hybridvoice.adatum.biz retornarão os endereços 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, enquanto os clientes que fizerem a mesma consulta de Seattle retornarão 10.10.1.8, 10.10.1.9 e 10.10.1.10.

> [!NOTE]
> Se o dispositivo CCE parece não ter as configurações atualizadas, verifique se o dispositivo consegue entrar em contato com o locatário via PowerShell remoto. Você pode usar o PowerShell remoto para verificar o status do aplicativo com Get-CsHybridPSTNAppliance ou usar o PowerShell no host CCE para verificar o status com Get-CcApplianceStatus.

  
## <a name="see-also"></a>Confira também
<a name="Example"> </a>

[Plano para bypass de mídia no Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
