---
title: Planejar Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Encontre informações sobre Skype for Business Cloud Connector Edition, um conjunto de VMs (Máquinas Virtuais) empacotados que implementam a conectividade PSTN local com Sistema de Telefonia (Cloud PBX).
ms.openlocfilehash: bff341213e9426f72fc0a78a9076b5b784871106
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728800"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planejar Skype for Business Cloud Connector Edition

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Encontre informações sobre Skype for Business Cloud Connector Edition, um conjunto de VMs (Máquinas Virtuais) empacotados que implementam a conectividade PSTN local com Sistema de Telefonia (Cloud PBX).

O Cloud Connector Edition pode ser a solução certa para sua organização se você ainda não tiver uma implantação existente do Lync Server ou Skype for Business Server. Se você ainda estiver investigando qual solução Sistema de Telefonia é ideal para sua empresa, consulte [Soluções de telefonia da Microsoft.](/microsoftteams/cloud-voice-landing-page)

Este documento descreve os requisitos do Cloud Connector Edition e topologias com suporte e ajuda você a planejar sua implantação do Cloud Connector Edition. Leia este artigo antes de configurar o ambiente do Cloud Connector. Quando estiver pronto para implantar e configurar o Cloud Connector Edition, consulte [Configure and manage Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

O Cloud Connector Edition 2.1 já está disponível. Se você ainda não tiver atualizado para 2.1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Você pode encontrar o arquivo de instalação em [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> A Microsoft dá suporte à versão anterior do Cloud Connector Edition por 60 dias após o lançamento de uma nova versão. A Microsoft dará suporte à versão 2.0.1 por 60 dias após o lançamento do 2.1 para permitir a atualização. Todas as versões anteriores a 2.0.1 não são mais suportadas.

Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de VMs (Máquinas Virtuais) empacotados que implementam a conectividade PSTN local com Sistema de Telefonia. Ao implantar uma topologia mínima Skype for Business Server em um ambiente virtualizado, os usuários em sua organização que estão na nuvem podem receber serviços PBX da nuvem da Microsoft, mas a conectividade PSTN é fornecida por meio da infraestrutura de voz local existente.

![Diagrama de topologia mostrando o Cloud PBX Gateway conectando o Cloud PBX a uma implantação local de Skype for Business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Como o Cloud Connector permite integrar os serviços Sistema de Telefonia ao seu ambiente de telefonia existente, por exemplo, PBX, dispositivos analógicos e Call Centers, você pode implementar uma migração em fases da sua solução de telefonia existente para Sistema de Telefonia.

Por exemplo, suponha que sua empresa tenha um Call Center sofisticado com funcionalidades específicas que Sistema de Telefonia não fornece. Você pode optar por deixar usuários do Call Center com a solução existente, mas mover outros usuários para Sistema de Telefonia.

O Cloud Connector fornecerá roteamento entre os usuários que estão no local e online, e você pode optar por usar seu próprio provedor PSTN com Sistema de Telefonia.

Considere o seguinte ao planejar sua implantação do Cloud Connector Edition:

- Para usar o Cloud Connector para tirar proveito das soluções de voz na nuvem, você precisará se inscrever em uma organização Microsoft 365 ou Office 365 que inclui Sistema de Telefonia. Se você ainda não tiver uma Microsoft 365 ou Office 365, poderá aprender a se inscrever aqui: [Microsoft 365 para Empresas](https://products.office.com/business/office). Observe que você precisará se inscrever em um plano que inclua Skype for Business Online.

- Para registrar dispositivos do Cloud Connector com o serviço Skype for Business Online e executar vários cmdlets, o Cloud Connector 2.0 e posterior requer uma conta Microsoft 365 ou Office 365 dedicada com os direitos de Administrador de Locatários do Skype for Business. As versões do Cloud Connector anteriores à 2.0 exigem uma conta Microsoft 365 ou Office 365 com direitos de administrador global do locatário.

- O Cloud Connector não exige uma implantação completa Skype for Business Server local.

    Atualmente, o Cloud Connector não pode coexistir com o Lync ou Skype for Business servidores locais. Se você quiser mover usuários existentes do Lync ou Skype for Business para o Microsoft 365 e continuar fornecendo telefonia local para seus usuários, considere Sistema de Telefonia conectividade local usando uma implantação de Skype for Business Server existente. Para obter mais informações, consulte [Plan your Sistema de Telefonia (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page.md) and Plan Sistema de Telefonia with [on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se você teve uma implantação anterior do Skype for Business ou do Lync Server e estendeu o esquema, não é necessário limpar o esquema para a implantação do Cloud Connector, desde que tenha removido todos os componentes do Skype for Business ou do Lync Server do seu ambiente.

- Seus usuários estão em casa online.

- Se sua organização configurou a Sincronização de Diretórios (DirSync), todas as contas de usuários que são planejadas para voz híbrida devem ser criadas primeiro na implantação local e sincronizadas com a nuvem.

- Você pode manter sua operadora PSTN atual, se necessário.

- Se você quiser fornecer conferência discada para usuários hospedados no Cloud Connector, poderá comprar a licença de conferência PSTN ou pagar à medida que for a oferta de Audioconferência da Microsoft.

- A licença de Audioconferência (ou pagar conforme você vai oferecer) também é necessária para escalonamentos de chamada. Se um usuário Skype for Business receber uma chamada de um usuário PSTN externo e quiser adicionar mais um participante a essa chamada (escalonar a chamada para uma conferência), a escalação será realizada por meio do serviço de Audioconferência da Microsoft.

- O Cloud Connector 2.0 e posterior agora suporta bypass de mídia. O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (Rede Telefônica Pública Comutado), um gateway ou Controlador de Borda de Sessão (SBC) e elimine o componente Cloud Connector Edition do caminho de mídia. Para obter mais informações, consulte [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- O Cloud Connector 2.1 e posterior oferece suporte ao monitoramento do Cloud Connector usando o Operations Management Suite (OMS). Para obter mais informações, consulte [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- O Cloud Connector está disponível em todos os países onde Office 365 Enterprise E5 está disponível.

Este artigo contém as seguintes seções:

- [Componentes do Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologias do Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisitos para implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informações que você precisa coletar antes da implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerações sobre o plano de discagem](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerações de alta disponibilidade](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Fluxo de mídia do Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoramento e solução de problemas](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Para saber mais](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componentes do Cloud Connector Edition
<a name="BKMK_Components"> </a>

Com o Cloud Connector Edition, você implanta um conjunto de VMs empacotados que contêm uma topologia Skype for Business Server mínima, que consiste em um componente de Borda, componente de Mediação e uma função de Armazenamento de Gerenciamento Central (CMS). Você também instalará um controlador de domínio, que é necessário para o funcionamento interno do Cloud Connector. Esses serviços são configurados para híbridos com sua organização Microsoft 365 ou Office 365 que inclui serviços Skype for Business Online.

![Componentes do Cloud Connector Edition.](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Os componentes do Cloud Connector fornecem a seguinte funcionalidade:

- **Componente de borda** - A comunicação entre a topologia local e os serviços online passa pelo componente de Borda, que inclui os seguintes componentes:

  - **Borda de Acesso** - Fornece roteamento SIP entre a implantação local e Skype for Business Online.

  - **Retransmissão de** mídia - Fornece roteamento de mídia entre o componente de Mediação e outros pontos de extremidade de mídia.

  - **Autenticação de Retransmissão de** Mídia / MRAS - Gera tokens para acesso à retransmissão de mídia.

- **Roteamento de** saída - Fornece balanceamento de carga do tráfego de voz entre gateways ou SBCs conectados a um dispositivo do Cloud Connector. As chamadas serão divididas de forma mesmo entre todos os gateways ou SBCs conectados ao dispositivo do Cloud Connector.

    Fornece roteamento para gateways com base em políticas. Somente as políticas globais baseadas nos números PSTN de destino (saída) são suportadas.

- **Função CMS (Armazenamento** de Gerenciamento Central) - Inclui o armazenamento de configuração para os componentes de topologia, incluindo a Transferência de Arquivos CMS.

- **Réplica do Armazenamento de Gerenciamento Central (CMS)** - Sincroniza informações de configuração do CMS DB global no servidor de função CMS.

- **Controlador de domínio** - Cloud Connector Active Directory Domain Services para armazenar todas as configurações globais e grupos necessários para implantar componentes do Cloud Connector. Uma floresta será criada para cada dispositivo do Cloud Connector. O controlador de domínio não deve ter conexões com o Active Directory de produção. Os serviços do Active Directory incluem:

  - Serviços de Domínio do Active Directory

  - Serviços de Certificado do Active Directory para emitir certificados internos

- **Componente de** mediação - Implementa o protocolo sip e o mapeamento de gateway de mídia entre Skype for Business e gateways PSTN. Inclui uma réplica CMS que sincroniza a configuração do banco de dados GLOBAL CMS.

## <a name="cloud-connector-edition-topologies"></a>Topologias do Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

Para fins dessa discussão, vamos nos referir a sites PSTN. Um site PSTN é uma combinação de dispositivos do Cloud Connector, implantados no mesmo local e com gateways PSTN comuns conectados a eles. Sites PSTN permitem:

- Forneça conectividade a gateways mais próximos de seus usuários.

- Permitir a escalabilidade implantando vários dispositivos do Cloud Connector em um ou mais sites PSTN.

- Permitir alta disponibilidade implantando vários dispositivos do Cloud Connector em um único site PSTN.

Este tópico apresenta sites PSTN. Para obter mais informações sobre como planejar seus sites PSTN, consulte [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Você pode implantar as seguintes topologias do Cloud Connector:

- Um único dispositivo Cloud Connector Edition por site PSTN. Essa topologia é recomendada apenas para fins de avaliação porque não oferece alta disponibilidade.

- Vários dispositivos Cloud Connector Edition por site PSTN para fornecer alta disponibilidade.

- Vários sites PSTN com vários dispositivos Cloud Connector Edition para fornecer escalabilidade com alta disponibilidade. Você pode implantar até 200 sites.

Ao planejar sua topologia, considere o seguinte:

- Com o Cloud Connector 2.0 e posterior, um site PSTN pode ter até 16 dispositivos do Cloud Connector. As versões anteriores suportam até quatro dispositivos por site.

- Há dois tipos de configurações de hardware testadas com o Cloud Connector:

  - A versão maior é capaz de lidar com grandes volumes de chamadas simultâneas e é suportada em todos os tipos de ambientes de produção.

  - A versão menor destina-se a ser executado em hardware inferior e pode ser usada para fins de avaliação ou para sites com volumes de chamada baixos. Se você implantar uma versão menor do Cloud Connector, ainda precisará estar atento aos requisitos de hardware de classe de produção (como fontes de alimentação duplas).

- Se você tiver o Cloud Connector versão 2.0 ou posterior e implantar a configuração máxima de 16 dispositivos (com hardware maior), seu site PSTN poderá lidar com até 8.000 chamadas simultâneas. Se você implantar a versão menor, o limite suportado será 800.

    Você também precisa dedicar alguns dispositivos para Alta Disponibilidade. A recomendação mínima é que um dispositivo deve ser reservado para Alta Disponibilidade.

  - Com a versão 2, se você implantar uma configuração 15+1, seu site PSTN poderá lidar com até 7.500 chamadas simultâneas.

  - Se você tiver uma versão anterior e implantar a configuração máxima de 3 + 1 (com hardware maior), seu site PSTN poderá lidar com até 1500 chamadas simultâneas. Se você implantar a versão menor, o limite suportado será 150.

-  Se você precisar ter mais chamadas por site PSTN, poderá dimensionar implantando sites PSTN adicionais no mesmo local.

> [!NOTE]
> A menos que seja notado, os diagramas e exemplos a seguir pressuem o uso da versão maior do Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Único dispositivo do Cloud Connector em um único site PSTN

O diagrama a seguir mostra um único dispositivo Cloud Connector Edition em um único site PSTN. Observe que o Cloud Connector consiste em quatro VMs instaladas em um computador host físico que está dentro de uma rede de perímetro para fins de segurança.

![Um Conector de Nuvem com um site PSTN.](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Vários dispositivos do Cloud Connector em um único site PSTN

 Para fins de escalabilidade e alta disponibilidade, você pode optar por ter várias edições do Cloud Connector em um único site PSTN, conforme mostrado no diagrama a seguir. Considere o seguinte:

- As chamadas são distribuídas em ordem aleatória entre os Conectores de Nuvem em um pool.

- Para fins de planejamento de capacidade, você deve considerar a capacidade de manipular a carga se um ou mais Cloud Connectors ficarem offline, com base nos seguintes cálculos:

  - **Caixas N+1.** Para a versão maior do Cloud Connector, as caixas N+1 suportam chamadas simultâneas de 500 N com \* disponibilidade de 99,8%.

    Para a versão menor do Cloud Connector, as caixas N+1 suportam chamadas simultâneas de 50 N com \* disponibilidade de 99,8%.

  - **Caixas N+2.** Para a versão maior do Cloud Connector, as caixas N+2 suportam chamadas simultâneas de 500 N com \* disponibilidade de 99,9%.

    Para a versão menor do Cloud Connector, as caixas N+2 suportam chamadas simultâneas de 50 N com \* disponibilidade de 99,9%.

![Dois conectores de nuvem dentro de um site PSTN.](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Vários sites PSTN com um ou mais Conectores de Nuvem por site

Você também pode optar por ter vários sites PSTN com uma ou mais edições do Cloud Connector em cada site. Se o site PSTN atingir o limite de chamadas simultâneas, você poderá adicionar outro site PSTN para lidar com a carga.

Vários sites PSTN também permitem que você forneça conectividade a gateways mais próximos de seus usuários. Por exemplo, suponha que você tenha gateways PSTN em Seattle e Amsterdã. Você pode implantar dois sites PSTN — um em Seattle, um em Amsterdã — e atribuir usuários para usar o site PSTN mais próximo a eles. Os usuários de Seattle serão roteados para o site e gateways PSTN de Seattle, enquanto os usuários em Amsterdã serão roteados para o site e gateways PSTN de Amsterdã:

![Cloud Connector Edition em 2 sites PSTN.](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisitos para implantação
<a name="BKMK_Requirements"> </a>

Antes de implantar o Cloud Connector Edition, certifique-se de ter o seguinte para seu ambiente:

- **Para o computador host -** As VMs do Cloud Connector devem ser implantadas em hardware dedicado executando Windows Server 2012 edição do Datacenter R2 (inglês) com a função Hyper-V habilitada.

    Para a versão 2.0 e posterior, o cartão de rede do computador host vinculado à opção Skype for Business Corpnet deve ter um endereço IP configurado na mesma sub-rede que as máquinas de rede corporativas do Cloud Connector.

- Para versões 2.1 e posteriores, o dispositivo host deve ter .NET Framework 4.6.1 ou posterior instalado.

- **Para as máquinas virtuais -** Uma imagem Windows Server 2012 ISO R2 (inglês) (.iso). O ISO será convertido em VHDs para as máquinas virtuais que serão Skype for Business Cloud Connector Edition.

- O hardware necessário para dar suporte à instalação das 4 VMs para cada Cloud Connector Edition em sua implantação. As seguintes configurações são recomendadas:

  - Processador duplo de 64 bits, seis núcleos (12 núcleos reais), 2,50 gigahertz (GHz) ou superior

  - RAM ECC de 64 gigabytes (GB)

  - Quatro discos de 600 GB (ou melhor) 10K RPM 128M cache SAS 6 Gbps, configurados em uma configuração RAID 5

  - Três adaptadores de rede de alta taxa de transferência RJ45 de 1 Gbps

- Se você optar por implantar a versão menor do Cloud Connector Edition que oferece suporte a até 50 chamadas simultâneas, você precisará do seguinte hardware:

  - Intel i7 4790 quad core com Gráficos Intel 4600 (sem gráficos high-end necessários)

  - 32 GB DDR3-1600 non ECC

  - 2: 1 TB 7200RPM SATA III (6 Gbps) no RAID 0

  - 2: Ethernet de 1 Gbps (RJ45)

- Se um servidor proxy for necessário no computador host para navegar na Internet, você deverá fazer as seguintes alterações de configuração:

  - Para ignorar o proxy, especifique as configurações do Proxy WinHTTP definidas com seu servidor proxy e uma lista de bypass, incluindo o "192.168.213". \* rede usada pelos serviços de Gerenciamentos do Cloud Connector e Skype for Business sub-rede da Corpnet, conforme definido em seu arquivo CloudConnector.ini. Caso contrário, a conectividade de gerenciamento falhará e impedirá a implantação e a recuperação automática do Cloud Connector. Veja a seguir um exemplo de comando de configuração winhttp: netsh winhttp set proxy "10.10.10.175:8080" bypass-list=" \* .local;1. \* ; 172.20. \* ;192.168.218. \* ' \<local\> ".

  - Especifique as configurações de proxy por máquina em vez de por usuário. Caso contrário, os downloads do Cloud Connector falharão. Você pode especificar configurações de proxy por máquina com uma alteração no Registro ou com a configuração da Política de Grupo da seguinte forma:

  - **Registro: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings]** ProxySettingsPerUser dword: 00000000

  - **Política de Grupo:** Modelos \> Administrativos do \> Computador Windows \> Componentes Internet Explorer: Fazer configurações de Proxy por máquina (em vez de por usuário)

- PBX/Tronco qualificado ou SBC/Gateway qualificado (recomenda-se um mínimo de dois gateways).

    O Cloud Connector dá suporte aos mesmos Controladores de Borda de Sessão (SBCs) certificados para Skype for Business. Para obter mais informações, consulte [Infraestrutura de Telefonia para Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).

- Uma conta de administrador de servidor local com permissões para instalar e configurar o Hyper-V nos servidores host. A conta deve ter permissões de administrador no servidor local onde o Hyper-V está instalado e configurado.

- Durante a implantação, você será solicitado a criar uma conta de administrador de domínio com permissões para criar e publicar a topologia no domínio do Cloud Connector.

- Os registros DNS externos, que são definidos no arquivo CloudConnector.ini incluído no pacote de instalação:

  - Registro DNS externo para serviço de Borda de Acesso do componente de Borda; por exemplo, ap. \<Domain Name\> . Você precisa de um registro por site PSTN. Esse registro deve conter endereços IP de todas as Bordas desse site.

- Uma Microsoft 365 ou Office 365 com todos os registros DNS e SRV necessários criados.

    > [!IMPORTANT]
    > Quando você integra seu locatário ao Cloud Connector Edition, o uso do sufixo de domínio padrão, .onmicrosoft.com, como um domínio SIP para sua organização não é suportado. > Não é possível usar sip.\<Domain Name\> como o nome da interface proxy do Cloud Connector Edge Access porque esse registro DNS é usado por Microsoft 365 e Office 365.

- Um certificado para a Borda externa obtida de uma Autoridade de Certificação (CA) pública.

- As regras de firewall para permitir o tráfego por meio das portas necessárias foram concluídas.

- Uma conexão com a Internet para o computador host e as VMs. O Cloud Connector baixa alguns softwares da Internet; portanto, você deve fornecer informações sobre gateway e servidor DNS para que a máquina host e as VMs do Cloud Connector possam se conectar à Internet e baixar o software necessário.

- Um módulo do PowerShell remoto do locatário instalado no computador host.

- As Skype for Business de administrador para executar o PowerShell remoto.

    > [!IMPORTANT]
    > A conta de administrador NÃO DEVE ter a autenticação multifa factor habilitada.

> [!NOTE]
> A implantação do Cloud Connector só tem suporte na plataforma Microsoft Hyper-V virtualizada. Outras plataformas, como VMware e Amazon Web Services, não são suportadas.

> [!NOTE]
> As diretrizes mínimas de hardware para executar o Cloud Connector se baseiam na capacidade básica de hardware (núcleos, MHz, gigabytes e assim por diante) com algum buffer para acomodar deficiências de desempenho intangíveis na arquitetura de qualquer computador. A Microsoft tem executado testes de carga de pior caso em hardware comercialmente disponível que atenderão às diretrizes mínimas. A qualidade da mídia e o desempenho do sistema são verificados. Os parceiros de dispositivos do Cloud Connector oficiais da Microsoft têm implementações de hardware específicas do Cloud Connector nas quais eles testaram de forma independente o desempenho e estão de acordo com a adequação de seu hardware para atender aos requisitos de carga e qualidade.

> [!NOTE]
> Os dispositivos produzidos por AudioCodes e Sonus modificaram o código e são executados Windows server Standard edition de servidores. Esses dispositivos têm suporte.

## <a name="information-you-need-to-gather-before-deployment"></a>Informações que você precisa coletar antes da implantação
<a name="BKMK_PlanDeployment"> </a>

Antes de começar sua implantação, você precisa determinar o tamanho da sua implantação, os domínios SIP que estão sendo atendidos e as informações de configuração para cada site PSTN que você planeja implantar. Para começar, você irá:

- Identifique todos os domínios SIP que serão atendidos por essa implantação com base nas URIs SIP em uso em sua empresa.

- Determine o número de sites PSTN que você precisa implantar.

- Verifique se você tem o hardware necessário para dar suporte às quatro VMs que você instalará para cada Edição do Cloud Connector.

Para cada site PSTN que você planeja implantar, você precisa:

- Criar nomes para todos os componentes em cada dispositivo do Cloud Connector (consulte [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definir intervalos de porta (consulte [Portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Criar registros DNS externos para o componente de Borda (consulte [Requisitos para implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determine seus requisitos de certificado para componente de Borda (consulte [Requisitos de certificado](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Portas e protocolos
<a name="BKMB_Ports"> </a>

Ao definir intervalos de porta de mídia, esteja ciente do seguinte:

- Os clientes sempre usam o intervalo de portas de 50000 a 50019 para tráfego de mídia— esse intervalo é predefinido no Skype for Business Online e não pode ser alterado.

- O componente de Mediação, por padrão, usará o intervalo de porta 49 152 a 57 500 para tráfego de mídia. No entanto, a conexão é estabelecida por meio de firewall interno e, por motivos de segurança, você pode limitar esse intervalo de portas em sua topologia. Você precisará de até quatro portas por chamada. Se você quiser limitar o número de portas entre o componente de Mediação e o gateway PSTN, também precisará configurar o intervalo de portas correspondente no gateway.

- Você deve implantar o Cloud Connector em uma rede de perímetro. Isso significa que você terá dois firewalls:

  - O primeiro firewall é externo entre a Internet e sua rede de perímetro.

  - O segundo firewall é interno entre a rede de perímetro e sua rede interna.

    Seus clientes podem estar na Internet ou na rede interna:

  - Os clientes na Internet se conectarão ao PSTN por meio do firewall externo por meio do componente de Borda.

  - Os clientes na rede interna se conectarão por meio do firewall interno ao componente de Mediação na rede de perímetro, que conectará o tráfego ao gateway SBC ou PSTN.

    Isso significa que você precisa abrir portas em ambos os firewalls.

As tabelas a seguir descrevem as portas e intervalos de porta para os firewalls externos e internos.

Esta tabela mostra as portas e os intervalos de porta para habilenciar a comunicação entre clientes na rede interna e o componente de Mediação:

**Firewall interno**



|**IP de Origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Componente de Mediação do Cloud Connector  <br/> |SBC/PSTN Gateway  <br/> |Qualquer  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Componente de Mediação do Cloud Connector  <br/> |Qualquer  <br/> |TCP 5068/ TLS 5067  <br/> |
|Componente de Mediação do Cloud Connector  <br/> |SBC/PSTN Gateway  <br/> |UDP 49 152 - 57 500  <br/> |Any\*\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Componente de Mediação do Cloud Connector  <br/> |Any\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Componente de Mediação do Cloud Connector  <br/> |Clientes internos  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50.000-50.019  <br/> Opcional.  <br/> |
|Componente de Mediação do Cloud Connector  <br/> |Clientes internos  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Clientes internos  <br/> |Componente de Mediação do Cloud Connector  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Clientes internos  <br/> |Componente de Mediação do Cloud Connector  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Esse é o intervalo de portas padrão no componente de Mediação. Para um fluxo de chamada ideal, quatro portas por chamada são necessárias.

\*\* Essa porta deve ser configurada no gateway SBC/PSTN; 5060 é um exemplo. Você pode configurar outras portas em seu gateway SBC/PSTN.

\*\*\* Observe que você também pode limitar o intervalo de portas em seu SBC/Gateway, se permitido pelo fabricante SBC/Gateway.

Para fins de segurança, você pode limitar o intervalo de portas para o componente de Mediação usando o cmdlet [Set-CsMediationServer.](/powershell/module/skype/set-csmediationserver?)

Por exemplo, o comando a seguir limita o número de portas que o componente de Mediação usará para tráfego de mídia para 50 000 - 51 000 para áudio (entrada e saída). O componente de Mediação poderá lidar com 250 chamadas simultâneas com essa configuração. Observe que você também pode querer limitar esse intervalo no gateway SBC/PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Para recuperar o nome do componente de Mediação e ver portas padrão, você pode usar o cmdlet [Get-CsService](/powershell/module/skype/get-csservice?) da seguinte forma:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

A tabela a seguir mostra as portas e intervalos de porta para habilenciar a comunicação entre o componente de Borda do Cloud Connector para o firewall externo. Esta tabela mostra uma recomendação mínima.

Nesse caso, todo o tráfego de mídia para a Internet fluirá por meio da Borda Online da seguinte forma: Ponto de extremidade do usuário-- \> Borda Online-- \> Borda do Cloud Connector:

**Firewall externo - configuração mínima**



|**IP de Origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |TCP(MTLS) 5061  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP(MTLS) 5061  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP 80  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |UDP 53  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP 53  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

A tabela a seguir mostra portas e intervalos de porta para habilenciar a comunicação entre o componente de Borda do Cloud Connector para o firewall externo. Esta tabela mostra a solução recomendada.

Nesse caso, todo o tráfego de mídia para o ponto final na Internet pode fluir diretamente para o componente de Borda do Cloud Connector. O caminho da mídia será o Ponto de Extremidade do Usuário - \> Borda do Conector de Nuvem.

> [!NOTE]
> Essa solução não funcionará se o ponto de extremidade do usuário estiver por trás de um NAT simétrico.

**Firewall externo - configuração recomendada**


|**IP de Origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |TCP(MTLS) 5061  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP(MTLS) 5061  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP 80  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |UDP 53  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |Qualquer  <br/> |TCP 53  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |TCP 50.000-59.999  <br/> |Qualquer  <br/> |
|Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |Qualquer  <br/> |
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |TCP 443; TCP 50.000-59.999  <br/> |
|Qualquer  <br/> |Interface Externa de Borda do Conector de Nuvem  <br/> |Qualquer  <br/> |UDP 3478; UDP 50.000 - 59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisitos de conectividade de Host com a Internet
<a name="BKMB_Ports"> </a>

O computador host deve ser capaz de alcançar recursos externos para instalar, atualizar e gerenciar com êxito o Cloud Connector. A tabela a seguir mostra os destinos e portas necessários entre o computador host e os recursos externos.

|Direção  <br/> |IP de origem  <br/> |IP de destino  <br/> |Porta de origem  <br/> |Porta de destino  <br/> |Protocolo  <br/> |Objetivo  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Saída  <br/> |Cloud Connector host IPs  <br/> |qualquer  <br/> |qualquer  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Saída  <br/> |Cloud Connector host IPs  <br/> |qualquer  <br/> |qualquer  <br/> |80, 443  <br/> |TCP  <br/> |Lista de Revogação de Certificados (CRL)  <br/> |
|Saída  <br/> |Cloud Connector host IPs  <br/> |qualquer  <br/> |qualquer  <br/> |80, 443  <br/> |TCP  <br/> |Atualização do Cloud Connector  <br/> Skype for Business Online  <br/> Admin PowerShell  <br/> Windows Update  <br/> |

Se regras mais restritivas são necessárias, consulte as seguintes URLs de lista de permitir:

- [URLs de lista de revogação de](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) certificado em [Office 365 URLs e intervalos de endereços IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Atualização: [como configurar um firewall para atualizações de software](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business Administrador online do PowerShell: \* .online.lync.com

    Se você precisar de uma exclusão de proxy para esse destino, precisará adicioná-lo à lista de bypass WinHTTP.

- Atualização do Cloud Connector: [Central](https://aka.ms/CloudConnectorInstaller)de Download [https://go.microsoft.com](https://go.microsoft.com) e [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Resolução de nome DNS para o componente edge
<a name="BKMB_Ports"> </a>

O componente edge precisa resolver os nomes externos de serviços Microsoft 365 ou Office 365 e os nomes internos de outros componentes do Cloud Connector.

Cada componente de Borda é um computador multi-homed com interfaces externas e internas voltadas. O Cloud Connector implanta servidores DNS no componente controlador de domínio dentro da rede de perímetro. Você pode apontar o Servidor de Borda para o Servidor DNS dentro do perímetro para todas as resoluções de nomes, mas você precisa habilitar o Servidor DNS do Cloud Connector para resolver nomes externos definindo uma zona DNS contendo um ou mais registros DNS A para consultas externas que se referem a consultas de nome para outros servidores DNS públicos.

No arquivo .ini, se você definir o nome FQDN para gateways do mesmo espaço de domínio que seu domínio SIP, a zona autoritativa para esse domínio SIP será criada no Servidor DNS dentro do perímetro. Se o Servidor de Borda for apontado para esse Servidor DNS para resolver nomes, o Edge nunca resolverá o _sipfederationtls.\<yourdomain\> Registro DNS, que é necessário para o fluxo de chamada. Nesse caso, a Microsoft recomenda que você forneça um Servidor DNS na interface externa de Borda para resolver as consultas de nome da Internet, e cada componente de Borda deve usar um arquivo HOST para resolver outros nomes de componentes do Cloud Connector em endereços IP.

> [!NOTE]
> Por motivos de segurança, recomendamos que você não aponte o servidor DNS do Cloud Connector para servidores internos no domínio de produção para resolução de nome.

### <a name="determine-deployment-parameters"></a>Determinar parâmetros de implantação
<a name="BKMK_SiteParams"> </a>

Primeiro, você precisa definir os seguintes parâmetros comuns de implantação:


|**Item**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Domínios SIP  <br/> |URI SIP em uso pelos usuários da empresa. Forneça todos os domínios SIP que serão atendidos por essa implantação. Você pode ter mais de um domínio SIP.  <br/> ||
|Número de sites PSTN  <br/> |O número de sites PSTN que você implantará.  <br/> ||

Para cada site PSTN que você planeja implantar, você precisará coletar as informações a seguir antes de começar a implantação. Você precisará fornecer essas informações quando atualizar o arquivo CloudConnector.ini.

Ao configurar informações de gateway, lembre-se do seguinte:

- Se você tiver apenas um gateway, remova a seção no arquivo .ini para o segundo gateway. Se houver mais de dois gateways, siga o formato existente para adicionar novos.

- Certifique-se de que o endereço IP e a porta dos gateways estão corretos.

- Para dar suporte ao HA de nível de gateway PSTN, mantenha o gateway secundário ou adicione gateways adicionais.

(Opcional) Para restringir os números de chamada de saída, atualize o valor LocalRoute.



|**Parâmetros de site**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Nome de domínio da máquina virtual  <br/> |Nome de domínio para os componentes internos do Cloud Connector. Esse domínio deve ser diferente do domínio de produção. O nome deve ser o mesmo em todos os dispositivos do Cloud Connector.  <br/> Nome no .ini: "VirtualMachineDomain"  <br/> |O domínio .local é preferencial.  <br/> |
|Nome do controlador de domínio do Cloud Connector  <br/> |Nome do controlador de domínio.  <br/> Nome no .ini: "ServerName"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|Máscara IP/sub-rede do controlador de domínio do Cloud Connector  <br/> |Endereço IP do controlador de domínio.  <br/> Nome no .ini: "IP"  <br/> ||
|Microsoft 365 ou Office 365 FQDNs de serviço online  <br/> |Deve ser o padrão na maioria dos casos para a instância de Microsoft 365 ou Office 365 mundo inteiro.  <br/> Nome no .ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business nome do site; por exemplo, Seattle.  <br/> Nome no .ini: "SiteName"  <br/> Para a Versão 1.4.1 e posterior, o nome do site deve ser diferente para cada site e o nome deve corresponder ao site PSTN, se existir, definido em Microsoft 365 ou Office 365. Observe que os sites PSTN serão criados automaticamente ao registrar o primeiro dispositivo em um site.  <br/> ||
|HardwareType  <br/> Versão 1.4.1 e posterior  <br/> |Tipo de hardware. O valor padrão é Normal. Você também pode definir como Mínimo.  <br/> ||
|Código do País  <br/> |Código de País para Discagem.  <br/> Nome no .ini: "CountryCode"  <br/> ||
|Cidade  <br/> |Cidade (Opcional).  <br/> Nome no .ini: "City"  <br/> ||
|Estado  <br/> |Estado (Opcional).  <br/> Nome no arquivo .ini: "State"  <br/> ||
|Endereço IP base da VM  <br/> |O endereço IP da VM base temporária que será usada para criar o VHDX para todas as máquinas virtuais do Cloud Connector. Esse IP deve estar na mesma sub-rede de rede corporativa de perímetro definida na próxima etapa e requer acesso à Internet. Certifique-se de definir o gateway padrão corporativo e o DNS que é table para a Internet.  <br/> Nome no .ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Versão 1.4.1 e posterior  <br/> |O endereço do Windows Server Update Services (WSUS)— um servidor intranet para hospedar atualizações do Microsoft Update.  <br/> Você pode deixar em branco se o WSUS não for necessário.  <br/> ||
|Máscara de sub-rede para rede interna  <br/> |O Cloud Connector configura uma rede IP para comunicação interna entre componentes do Cloud Connector. A borda também deve ser conectada a outra sub-rede que permita a conectividade com a Internet.  <br/> Nome no .ini: "CorpnetIPPrefixLength" em "Parâmetros para um pool de rede VM"  <br/> ||
|Máscara de sub-rede para rede externa  <br/> |Para a rede externa do componente Edge.  <br/> Nome no .ini: "InternetIPPrefix" em "Parâmetros para um pool de rede VM"  <br/> ||
|Nome da opção para rede interna  <br/> |Nome da opção que será usada para a rede interna do Cloud Connector.  <br/> Na maioria dos casos, o valor sugerido padrão pode ser usado.  <br/> Nome no .ini: "CorpnetSwitchName" em "Parâmetros para um pool de rede VM  <br/> ||
|Nome da opção para rede externa  <br/> |Nome da opção que será usada para a rede externa do Cloud Connector.  <br/> Na maioria dos casos, o valor sugerido padrão pode ser usado.  <br/> Nome no .ini: "InternetSwitchName" em "Parâmetros para um pool de rede VM  <br/> ||
|Gateway padrão para rede interna  <br/> |Esse gateway deve fornecer acesso à Internet (a Internet também requer a configuração do servidor DNS) e será configurado em interfaces internas dos componentes do Cloud Connector.  <br/> Nome no .ini: "CorpnetDefaultGateway" em "Parâmetros para um pool de rede VM  <br/> ||
|Gateway padrão para interface externa do componente de Borda  <br/> |Será configurado na interface externa do componente de Borda.  <br/> Nome no .ini: "InternetDefaultGateway" em "Parâmetros para um pool de rede VM  <br/> ||
|Servidor DNS para rede interna  <br/> |Será configurado na interface interna da VM temporária. Deve fornecer resolução de nomes para nomes da Internet. Sem fornecer um servidor DNS, a conexão com a Internet falhará e a implantação não terminará.  <br/> Nome no .ini: "CorpnetDNSIPAddress" em "Parâmetros para um pool de rede VM  <br/> ||
|Servidor DNS para interface externa do componente de Borda  <br/> |Será configurado na interface externa do Edge.  <br/> Nome no .ini: "InternetDNSIPAddress" em "Parâmetros para um pool de rede VM  <br/> ||
|Nome da opção de gerenciamento  <br/> |A opção de gerenciamento é uma opção temporária que será criada automaticamente e que será usada para a configuração do Cloud Connector durante a implantação. Ele será desconectado automaticamente após a implantação. Deve ser uma sub-rede diferente de qualquer outra rede usada no Cloud Connector.  <br/> Na maioria dos casos, o valor sugerido padrão pode ser usado.  <br/> Nome no .ini: "ManagementSwitchName" em "Parâmetros para um pool de rede VM  <br/> ||
|Endereço de sub-rede de gerenciamento/máscara de sub-rede  <br/> |A sub-rede de gerenciamento é uma sub-rede temporária que será criada automaticamente e que será usada para a configuração do Cloud Connector durante a implantação. Ele será removido automaticamente após a implantação. Deve ser uma sub-rede diferente de qualquer outra rede usada no Cloud Connector.  <br/> Nomes no .ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" em "Parâmetros para um pool de rede VM  <br/> ||
|Máquina cms (Armazenamento de Gerenciamento Central)  <br/> |FQDN único usado para o Armazenamento de Gerenciamento Central (CMS). O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no .ini: "ServerName" em "Parameters for Primary Central Management Service  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> (Nome do Pool CMS = Nome do Servidor)  <br/> |
|Endereço IP do computador CMS  <br/> |Endereço IP do CMS Server (interno na rede de perímetro).  <br/> Nome no arquivo INI: "IP" em "Parameters for Primary Central Management Service  <br/> ||
|Nome do Compartilhamento de Arquivos  <br/> |Nome do Compartilhamento de Arquivos a ser criado no servidor CMS para Skype for Business dados de replicação (por exemplo, CmsFileStore).  <br/> Na maioria dos casos, o valor sugerido padrão pode ser usado.  <br/> Nome no .ini: "CmsFileStore" em "Parameters for Primary Central Management Service  <br/> ||
|Nome do pool do componente de mediação  <br/> |Pool Name of Mediation component. Insira somente o nome netbios. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no .ini: "PoolName" em "Parâmetros para um pool de Servidores de Mediação"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|Nome do componente de mediação  <br/> |Nome do Componente do Componente de Mediação 1. Insira somente o nome netbios. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no .ini: "ServerName" em "Parâmetros para um pool de Servidores de Mediação"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|Endereço IP do computador do componente de mediação  <br/> |Ip Corpnet interno para componente de mediação (interno na rede de perímetro).  <br/> Nome no .ini: "IP" em "Parâmetros para um pool de Servidores de Mediação"  <br/> ||
|Nome interno do pool de borda  <br/> |Nome do Pool do componente de Borda. Insira somente o nome netbios. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no .ini: "InternalPoolName" em "Parâmetros para um pool de Servidores de Borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|Nome interno do Servidor de Borda  <br/> |Nome do Componente do Componente de Borda. Insira somente o nome netbios. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no .ini: "InternalServerName" em "Parâmetros para um pool de Servidores de Borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|IP interno do servidor de borda  <br/> |Componente IP de Borda de rede de perímetro interno para se comunicar com outros componentes do Cloud Connector.  <br/> Nome no .ini: "InternalServerIPs" em "Parâmetros para um pool de Servidores de Borda"  <br/> ||
|Nome Externo do Pool de Acesso  <br/> |Nome da Borda de Acesso; por exemplo, AP. Esse nome deve corresponder ao nome fornecido para o certificado SSL. Insira somente o nome netbios. O nome de domínio SIP será usado para gerar o FQDN. Um nome de pool externo será usado para todos os componentes de Borda no pool. Um pool de Acesso de Borda é necessário por site PSTN.  <br/> Nome no .ini: "ExternalSIPPoolName" em "Parâmetros para um pool de Servidores de Borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> "sip" é reservado e, portanto, não pode ser usado como o nome.  <br/> O nome FQDN gerado deve corresponder ao nome fornecido para o certificado SSL.  <br/> |
|IP externo de Borda de Acesso  <br/> |Componente IP externo de Borda - IP público se nenhum NAT estiver disponível ou IP convertido (especifique ambos os endereços se mapeado).  <br/> Nome no .ini: "ExternalSIPIPs" em "Parâmetros para um pool de Servidores de Borda"  <br/> ||
|Nome do Retransmissão de Mídia  <br/> |Nome da Borda de Retransmissão de Mídia de Vídeo de Áudio; por exemplo, MR. Um nome de pool externo será usado para todos os componentes de Borda em um pool. Um pool de Retransmissão de Mídia de Borda é necessário por site PSTN.  <br/> Nome no .ini: "ExternalMRFQDNPoolName" em "Parâmetros para um pool de Servidores de Borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome netbios.  <br/> |
|IP externo da borda de retransmissão de mídia  <br/> |Atualmente, há suporte para apenas um IP, portanto, esse será o mesmo IP do Access Edge, ip público ou mapeado (especifique ambos os endereços se mapeado). Pode ser o mesmo endereço do componente de Borda IP externo de Borda de Acesso. Observe que se Edge estiver atrás do NAT, você também precisará especificar o valor para o próximo parâmetro.  <br/> Nome no .ini: "ExternalMRIPs" em "Parâmetros para um pool de Servidores de Borda"  <br/> ||
|IP externo da Borda de Retransmissão de Mídia (se a Borda estiver atrás do NAT)  <br/> |Se o Edge estiver atrás do NAT, você também precisará especificar o endereço público do dispositivo NAT.  <br/> Nome no .ini: "ExternalMRPublicIPs" em "Parâmetros para um pool de Servidores de Borda"  <br/> ||
|Voice Gateway 1 Make and Model  <br/> |Especifique a make e o modelo do gateway SBC/Voice. Observe que você pode conectar um dispositivo ou tronco SIP na lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Voice Gateway 2 Make and Model (copie esta linha se você tiver mais de 2 gateways)  <br/> |Especifique a make e o modelo do gateway de voz. Observe que você pode conectar um dispositivo na lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Nome do Gateway de Voz 1  <br/> |Usado para gerar o FQDN do computador com Domínio AD. Obrigatório se o TLS for usado entre o componente de Mediação e o Gateway de Voz. Se você não planeja usar FQDN, por exemplo, o TLS não é necessário ou o Gateway de Voz não dá suporte à conexão usando FQDN (somente IP) — especifique.  <br/> ||
|Nome do Gateway de Voz 2 (copie esta linha se você tiver mais de 2 gateways)  <br/> |Usado para gerar o FQDN do computador com Domínio AD. Obrigatório se o TLS for usado entre o componente de Mediação e o Gateway de Voz. Se você não planeja usar FQDN, por exemplo, o TLS não é necessário ou o Gateway de Voz não dá suporte à conexão usando FQDN (somente IP) — especifique.  <br/> ||
|Endereço IP do Gateway de Voz 1  <br/> |Endereço IP do Gateway de Voz.  <br/> ||
|Endereço IP do Gateway de Voz 2 (copie esta linha se você tiver mais de 2 gateways)  <br/> |Endereço IP do Gateway de Voz.  <br/> ||
|Porta do Gateway de Voz 1 # (copie esta linha se você tiver mais de 2 gateways)  <br/> |Porta que o tronco SIP do Gateway de Voz escutará, por exemplo, 5060.  <br/> ||
|Porta do Voice Gateway 2 #  <br/> |Porta que o tronco SIP do Gateway de Voz escutará, por exemplo, 5060.  <br/> ||
|Protocolo gateway de voz 1 para tráfego SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocolo gateway de voz 2 para tráfego SIP (copie esta linha se você tiver mais de 2 gateways)  <br/> |TCP ou TLS.  <br/> ||
|Intervalo de portas de Mídia Externa para tráfego de e para o componente de Borda  <br/> |Intervalo de portas TCP/UDP para tráfego de mídia de e para a interface externa de borda. Deve sempre começar de 50.000. Consulte "Portas e Protocolos" para obter mais informações.  <br/> |50000 - 59 999  <br/> |
|Intervalo de portas de mídia para se comunicar com/a partir do componente de Mediação por meio do firewall interno  <br/> |Intervalo de portas UDP que o componente de Mediação usará para se comunicar com clientes e gateways (recomendação 4 portas por chamada).  <br/> ||
|Intervalo de portas de mídia para se comunicar com/Skype for Business cliente por meio de firewall interno  <br/> |Para fins de planejamento, não é possível mudar. As portas precisam ser abertas no firewall interno para se comunicar entre Skype for Business clientes dentro da rede interna e com o componente de Mediação.  <br/> |50 000- 50 019  <br/> |
|Senha de Certificado Público  <br/> |Deve ser fornecido no script.  <br/> ||
|Cofre Senha do Administrador do Modo  <br/> Versão 1.4.2 somente  <br/> |Cofre de administrador de modo para domínio CC interno.  <br/> ||
|Senha do Administrador de Domínio do Cloud Connector  <br/> Versão 1.4.2 somente  <br/> |Senha para Administrador de Domínio do Cloud Connector (diferente do domínio de produção). O nome de usuário é Administrador. Não é possível alterar o nome de usuário.  <br/> ||
|Senha do Administrador de Máquinas Virtuais  <br/> Versão 1.4.2 somente  <br/> |Usado para configurar a rede de gerenciamento durante a implantação.  <br/> O nome de usuário é Administrador. Não é possível alterar o nome de usuário.  <br/> ||
|CABackupFile  <br/> Versão 2.0 e posterior  <br/> |Usado para salvar o Serviço de Autoridade de Certificação do servidor do Active Directory em um arquivo ao implantar vários dispositivos em um site do Cloud Connector. Certifique-se de usar a mesma senha para todos os dispositivos em um site do Cloud Connector para importar o arquivo de backup da CA para o novo dispositivo adicionado com êxito.  <br/> ||
|CCEService  <br/> Versão 2.0 e posterior  <br/> |Usado para o serviço de Gerenciamento do Cloud Connector; precisa de acesso ao diretório de sites do Cloud Connector. Certifique-se de usar a mesma senha para todos os dispositivos em um site do Cloud Connector.  <br/> ||
|Microsoft 365 ou Office 365 administrador de locatários  <br/> | A conta é usada pelo Cloud Connector para atualizar e gerenciar configurações de locatário para o Cloud Connector: <br/>  Versão 2.0 e posterior: Credenciais para uma conta Microsoft 365 ou Office 365 com Skype for Business administrador. <br/>  Versões anteriores à 2.0: Credenciais para uma conta Microsoft 365 ou Office 365 com direitos de Administrador Global de Locatários. <br/> ||
|Habilitar o suporte a REFER  <br/> |Isso definirá se o suporte SIP REFER está habilitado ou desabilitado na Configuração do Tronco para seu IP/PBX. O valor padrão é True. Se o Gateway IP/PBX for compatível com o suporte a REFER, deixe-o como True. Se isso não acontecer, esse valor precisará ser alterado para False. Se você não tiver certeza se seu gateway dá suporte a REFER, consulte [Qualified IP-PBXs and Gateways](../../../SfbPartnerCertification/certification/infra-gateways.md).   <br/> ||
|EnableFastFailoverTimer  <br/> Versão 2.0 e posterior  <br/> |Com o valor padrão "True", se as chamadas de saída não são atendidas pelo gateway dentro de 10 segundos, elas serão roteadas para o próximo gateway disponível; se não houver troncos adicionais, a chamada será retirada automaticamente.  <br/> No entanto, em uma organização com redes lentas e respostas de gateway, ou quando o processo de estabelecimento de chamadas leva mais de 10 segundos, isso pode resultar em chamadas sendo retiradas desnecessariamente.  <br/> Ao fazer chamadas para alguns países, por exemplo, os Emirados Árabes Unidos ou o Afeganistão, o processo de estabelecimento de chamadas pode levar mais de 10 segundos. Você precisará alterar o valor para False se encontrar problemas semelhantes. Não se esqueça de alterar a configuração correspondente no SBC ou Gateway conectado.  <br/> O valor pode ser True ou False. O valor padrão é True.  <br/> ||
|ForwardCallHistory  <br/> Versão 2.0 e posterior  <br/> | Esse parâmetro é usado para ativar os headers SIP usados para relatar o chamador inicial em cenários de Toque Simultâneo, Encaminhamento de Chamada e Transferência de Chamada. A definição do parâmetro como True ativará dois headers SIP: <br/>  History-Info <br/>  Referred-By <br/>  O History-Info de History-Info é usado para retargeting de solicitações SIP e "fornecer(s) um mecanismo padrão para capturar as informações de histórico de solicitação para habilitar uma ampla variedade de serviços para redes e usuários finais" ([RFC 4244 - Seção 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Para as interfaces de tronco do Cloud Connector, isso é usado em cenários de toque simultâneo e encaminhamento de chamada.  <br/>  O valor pode ser True ou False. O valor padrão é False. <br/> ||
|Encaminhar PAI  <br/> Versão 2.0 e posterior  <br/> |PAI é uma extensão privada para SIP que permite que os servidores SIP afirmem a identidade de usuários autenticados. Para o provedor de tronco SIP, o PAI pode ser usado para fins de cobrança se History-Info e Referred-By não estão presentes. Quando Forward P-Asserted-Identity estiver habilitado na configuração, o Servidor de Mediação encaminhará os headers PAI com SIP Tel URI do Cloud Connector para o &amp; Tronco SIP. O Servidor de Mediação encaminhará os headers PAI com números E.164 da tel URI recebidos SOMENTE no tronco &amp; SIP para o Cloud Connector. O Servidor de Mediação também encaminhará quaisquer headers de Privacidade recebidos em qualquer direção. Se a Solicitação SIP enviada pelo Servidor de Mediação incluir um header de Privacidade do formulário - "Privacidade: id" em conjunto com o header pai, a identidade afirmada deverá ser mantida privada fora do domínio de confiança de rede.  <br/> O valor pode ser True ou False. O valor padrão é False.  <br/> ||

### <a name="certificate-requirements"></a>Requisitos de Certificação
<a name="BKMK_Certs"> </a>

Cada componente de Borda requer um certificado de uma autoridade de certificação pública. Os certificados devem ter uma chave privada exportável para copiar entre componentes de Borda. Para atender aos requisitos de certificado, você precisará decidir entre as seguintes opções e fornecer o Nome do Assunto (SN) e o Nome Alternativo do Assunto (SAN) para o certificado.

 **Se você tiver um único domínio SIP:**

- **Opção 1.** O Nome do Assunto deve conter o nome do pool atribuído aos componentes de Borda. Observe que o Nome do Assunto não pode ser sip.sipdomain.com porque esse nome é reservado para o componente Skype for Business Edge online. A SAN deve conter sip.sipdomain.com e o nome do pool de Borda de acesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opção 2.** Se você quiser usar um único certificado Curinga em todos os servidores de pool de Borda implantados, poderá usar uma entrada SAN curinga de .sipdomain.com em vez do nome do pool de Borda no \* certificado. O nome do assunto pode ser o nome do pool de Borda de acesso de qualquer um dos pools de Borda que você implantou:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para sip. \<sipdomain\> . com porque esse nome pertence à Microsoft 365 ou Office 365 implantação.

> [!NOTE]
> Se você quiser usar um único certificado para todos os pools de Borda implantados em sua organização e não puder usar um certificado curinga conforme definido na opção 2, será necessário incluir o FQDN para todos os pools de Borda implantados no nome SAN no certificado.

 **Se você tiver vários domínios SIP:**

Você precisará adicionar sip.sipdomain.com para cada domínio SIP e o nome dos pools de Borda de acesso por domínio ( pode ser um pool físico, mas com nomes diferentes). Veja a seguir um exemplo de entradas SN e SAN em um cenário de domínio de vários sip:

- **Opção 1.** O Nome do Assunto deve conter o nome do pool atribuído aos componentes de Borda. Observe que o Nome do Assunto não pode ser sip.sipdomain.com porque esse nome é reservado para o componente Skype for Business Edge online. A SAN deve conter sip.sipdomain.com e o nome do pool de Borda de acesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opção 2.</strong> Se você quiser usar um único certificado Curinga em todos os servidores de pool de Borda implantados, poderá usar uma entrada SAN curinga de .sipdomain.com em vez do nome do pool de Borda no \* certificado. O nome do assunto pode ser o nome do pool de Borda de acesso de qualquer um dos pools de Borda que você implantou:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para sip. \<sipdomain\> . com porque esse nome pertence à Microsoft 365 ou Office 365 implantação.

Para fins de implantação, você pode usar a seguinte tabela:

|**Opção**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Qual opção você usará para sua implantação?  <br/> |Opção 1 ou 2  <br/> ||
|SN  <br/> |Forneça o SN para seu certificado  <br/> ||
|SAN  <br/> |Fornece o SAN para seu certificado  <br/> ||

Se você estiver usando o TLS entre o gateway e o Servidor de Mediação, você precisará obter o Certificado Raiz ou a cadeia de Certificados completa para o certificado atribuído ao gateway.

## <a name="dial-plan-considerations"></a>Considerações sobre o plano de discagem
<a name="BKMK_DailPlan"> </a>

O Cloud Connector requer o uso de um plano de discagem online. Para obter mais informações sobre como configurar um plano de discagem online, consulte [O que são planos de discagem?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerações de alta disponibilidade
<a name="BKMK_HA"> </a>

Quando você implanta o Cloud Connector Edition para alta disponibilidade, você implanta pelo menos dois dispositivos que atuam como backup uns dos outros. Cada dispositivo consiste em quatro componentes: Edge, Mediation, Central Management Store (CMS) e controlador de domínio.

Em geral, se um componente dentro de um dispositivo cair, o Cloud Connector Edition poderá continuar a manipular chamadas, mas você deve considerar o seguinte:

- **Considerações sobre componentes de controle de domínio, CMS e mediação**

    Suponha que o CMS ou o componente do controlador de domínio em um dispositivo cai. O dispositivo ainda pode manipular chamadas de entrada e saída, mas se você reiniciar um componente de Mediação quando o controlador de domínio ou o componente CMS não estiver acessível, a mediação não funcionará. O mesmo se aplica à reinicialização do componente CMS quando o controlador de domínio está para baixo.

    **Recomendação:** Antes de reiniciar componentes, verifique a disponibilidade dos outros componentes no dispositivo.

- **Considerações sobre componentes de borda**

    Se o componente Edge em um dispositivo não estiver disponível, o comportamento para chamadas de entrada e saída será diferente da seguinte forma:

  - **Chamada de saída**— uma chamada do usuário na Internet para uma rede PSTN.

    O mecanismo de distribuição de chamadas na nuvem identificará que um componente de Borda está inocutado e encaminhará todas as chamadas para outro dispositivo, para que a chamada de saída seja bem-sucedida.

  - **Chamada de entrada**— uma chamada da rede PSTN para um usuário que está em uma rede local ou na Internet.

     Se o componente de Borda do dispositivo que recebeu a chamada não estiver funcionando, as chamadas de entrada para esse dispositivo não serão bem-sucedidas porque o componente de Mediação não pode redirecionar a chamada para o componente de Borda no outro dispositivo.

    **Recomendação:** Ter um sistema de monitoramento no local. Depois de identificar um mau funcionamento do componente de Borda, desligue todos os componentes no dispositivo em que o componente de Borda não está disponível.

## <a name="cloud-connector-media-flow"></a>Fluxo de mídia do Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Os diagramas a seguir delineam o fluxo de uma chamada de saída e de entrada por meio do Cloud Connector Edition. Essas informações são úteis para entender como a conectividade é estabelecida.

No primeiro diagrama, um usuário interno coloca uma chamada de saída da seguinte maneira:

1. Dave, um usuário morou online, mas agora na rede interna, coloca uma chamada para um usuário PSTN externo.

2. Rotas de tráfego SIP para Skype for Business Online.

3. Skype for Business Online executa uma Busca de Número Reverso do número. A Análise de Número Reverso falha porque esse número não pertence a ninguém na Skype for Business organização.

4. A chamada é roteada para o componente de Borda (SIP e Fluxo de mídia via Borda Online primeiro; A mídia irá para o componente de Mediação por meio do firewall interno).

5. Se a rota existir, o componente de Borda retransmite o tráfego para o componente de Mediação na rede de perímetro.

6. O componente de Mediação envia o tráfego para o gateway PSTN.

![Fluxo de mídia de saída para o Cloud Connector.](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

No próximo diagrama, um usuário interno recebe uma chamada de entrada da seguinte maneira:

1. O gateway PSTN recebe uma chamada para o usuário Dave que está em casa online, mas agora está na rede interna.

2. O tráfego SIP é roteado para o componente de Mediação.

3. O componente de Mediação envia o tráfego SIP para o componente de Borda e, em seguida, ele vai para Skype for Business Online.

4. Skype for Business Online executa uma Busca de Número Reverso do número e descobre que esse é o usuário Dave.

5. A sinalização SIP vai para todos os pontos de presença de Dave.

6. O tráfego de mídia será estabelecido entre o gateway e o componente de Mediação e entre o componente de Mediação e o ponto final.

![Entrada de mídia Flow para o Cloud Connector.](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoramento e solução de problemas
<a name="BKMK_Monitor"> </a>

O mecanismo de monitoramento e solução de problemas é instalado automaticamente com todos os dispositivos do Cloud Connector. O mecanismo detecta os seguintes eventos:

- Uma ou mais máquinas virtuais de um dispositivo Cloud Connector não estão conectadas a uma opção virtual interna ou da Internet.

- Uma ou mais máquinas virtuais de um dispositivo Cloud Connector estão no status salvo ou interrompido.

- Serviços que não estão em execução.

  Se um dos seguintes eventos for detectado, todo o dispositivo do Cloud Connector será esvaziado e marcado como offline para evitar a tentativa de estabelecer chamadas para um dispositivo com mau funcionamento. Os recursos de recuperação automática do Cloud Connector subsequentemente restaurarão os serviços e marcarão o dispositivo como online. Se a recuperação automática falhar por algum motivo, consulte [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

  - Na máquina virtual do Armazenamento de Gerenciamento Central:

     - Skype for Business Agente replicador mestre

     - Skype for Business Replica Replicator Agent

  - Na máquina virtual do Servidor de Mediação:

     - Skype for Business Replica Replicator Agent

     - Skype for Business Server Mediação

  - Na Máquina Virtual do Servidor de Borda

     - Skype for Business Replica Replicator Agent

     -  Skype for Business Server Borda de Acesso

     - Skype for Business Server Borda de áudio/vídeo

     - Skype for Business Server Autenticação de áudio/vídeo

     - Skype for Business Server Borda de WebConferência

- Regra de entrada Windows firewall para "CS RTCSRV" no Edge, "CS RTCMEDSRV" no Servidor de Mediação está desabilitado.

O Cloud Connector 2.1 e posterior oferece suporte ao monitoramento do Cloud Connector usando o Operations Management Suite (OMS). Para obter mais informações, consulte [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_MoreInfo"> </a>

Para obter mais informações, confira o seguinte:

- [Soluções de telefonia da Microsoft](/microsoftteams/cloud-voice-landing-page)

- [Configurar e gerenciar Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Plano para bypass de mídia no Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Implantar bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
