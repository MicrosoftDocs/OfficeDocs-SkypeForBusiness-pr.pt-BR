---
title: Implantar o bypass de mídia no Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber sobre etapas para implantar o bypass de mídia com o conector de nuvem Edition versão 2.0 e posteriores.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Implantar o bypass de mídia no Cloud Connector Edition
 
Leia este tópico para saber sobre etapas para implantar o bypass de mídia com o conector de nuvem Edition versão 2.0 e posteriores. 
  
Bypass de mídia permite que um cliente enviar mídia diretamente para o próximo salto de rede de telefônica pública comutada (PSTN) — um gateway ou controlador de borda de sessão (SBC) — e eliminar o componente de edição do conector de nuvem do caminho de mídia. Consulte também [Planejar media bypass na nuvem conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Habilitar bypass de mídia

Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web do bypass de mídia e ativar o bypass de mídia na configuração do locatário. O serviço Web de bypass de mídia é implantado automaticamente em cada Servidor de Mediação. Um administrador de locatário precisa escolher um nome para um serviço de voz híbrido (site), e esse nome deve ser de um domínio SIP registrado para voz híbrida. O nome do serviço deve ser o mesmo em todos os aparelhos de conector de nuvem e todos os sites PSTN, independentemente da localização do cliente. O serviço Web só deve estar disponível internamente na rede.
  
O administrador do locatário deve configurar um registro A DNS no Active Directory da produção interna. Se você tiver um ambiente complexo de vários local, consulte o exemplo [exemplo: registros DNS do site da web em ambientes de vários locais complexos de bypass de mídia](deploy-media-bypass-in-cloud-connector.md#Example). O registro DNS deve resolver apenas clientes da rede interna; ele não deve resolver clientes da rede externa.
  
Depois de configurar o DNS, conecte-se ao Skype for Business Online usando o PowerShell remoto com as credenciais de administrador do Skype for Business. Para obter mais informações, consulte [Connecting to Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Habilitando o bypass de mídia em um processo de duas etapas. O cmdlet New-CsNetworkMedia não salva imediatamente a nova configuração; ele só cria as configurações na memória. O objeto criado por este cmdlet deve ser salvo como uma variável, e então atribuído à propriedade MediaBypassSettings da configuração da rede. Para obter mais informações, consulte [exemplo: registros DNS do site da web em ambientes de vários locais complexos de bypass de mídia](deploy-media-bypass-in-cloud-connector.md#Example).
  
A replicação entre o local e os componentes online pode levar até 24 horas, portanto, a Microsoft recomenda que você execute os comandos necessários antes de habilitar os usuários.
  
## <a name="confirm-media-bypass-settings"></a>Confirmar as configurações de bypass de mídia

Você pode verificar as configurações de bypass de mídia da seguinte maneira.  
  
Para verificar a replicação on-line para seu pool de locatário, execute o seguinte comando no PowerShell remoto:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

Para verificar a replicação do local, conecte-se para os servidores de mediação do conector de nuvem, execute o seguinte comando no PowerShell e confirme que Enabled = True e AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Para verificar as configurações do cliente, sair do Skype para o cliente de negócios, entrar novamente e confirme se o cliente recebeu a URL do serviço da seguinte maneira:
  
1. Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.  
    
2. Procurar hybridconfigserviceinternalurl e confirme que a URL corresponda ao definido por você.
    
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

Depois de fazer a alteração, pode levar algum tempo até que as alterações sejam replicadas em todos os Cloud Connectors. Para verificar o status da replicação, execute o seguinte cmdlet do PowerShell nos servidores de mediação do conector de nuvem: 
  
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

O administrador também precisará remover os endereços da web para o bypass de mídia dos servidores DNS internos. Após a alteração, ele pode levar algum tempo para que as alterações replicar para todos os aparelhos de conector de nuvem. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Exemplo: registros DNS do site de bypass de mídia em ambientes complexos multissites.
<a name="Example"> </a>

Os clientes receberão o endereço web do serviço de bypass de mídia de um servidor DNS interno. O nome do serviço da web será o mesmo em todos os aparelhos de conector de nuvem e sites de PSTN do conector de nuvem. Em um ambiente complexo multissites, recomendamos usar a política de DNS do Windows 2016 para localização geográfica com base em gerenciamento de tráfego para que os clientes possam ser redirecionados para o serviço Web que seja local para a sua rede. 
  
Para obter mais informações sobre políticas de DNS do Windows 2016, consulte [Usar diretivas de DNS para o gerenciamento de tráfego com base em localização geográfica com servidores primários](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).
  
Veja a seguir um exemplo de configuração para uma empresa com vários sites usando a Política DNS do Windows 2016 para Localização geográfica com base em gerenciamento de tráfego.
  
O nome para o serviço de desvio é 'hybridvoice.adatum.biz'.
  
O site no Amsterdã tem quatro aparelhos de nuvem conector implantados com os seguintes endereços IP do servidor de mediação:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
O site em Seattle tem três aparelhos de nuvem conector implantados com os seguintes endereços IP do servidor de mediação:
  
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
  
## <a name="see-also"></a>Ver também
<a name="Example"> </a>

#### 

[Planejar o bypass de mídia na nuvem conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

