---
title: Planejar o Skype for Business Cloud Connector Edition
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Encontre informações sobre o Skype for Business Cloud Connector Edition, um conjunto de VMs (máquinas virtuais) empacotadas que implementam a conectividade PSTN local com o sistema de telefonia (Cloud PBX).
ms.openlocfilehash: d2b7f4203da082112b846cc3f12f57dd7758fc82
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220081"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planejar o Skype for Business Cloud Connector Edition

Encontre informações sobre o Skype for Business Cloud Connector Edition, um conjunto de VMs (máquinas virtuais) empacotadas que implementam a conectividade PSTN local com o sistema de telefonia (Cloud PBX).

O Cloud Connector Edition pode ser a solução certa para sua organização se você ainda não tiver uma implantação existente do Lync Server ou do Skype for Business Server. Se você ainda estiver investigando a solução de sistema de telefonia adequada para sua empresa, confira [soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

Este documento descreve os requisitos da edição do Cloud Connector e as topologias com suporte e ajuda a planejar sua implantação do Cloud Connector Edition. Certifique-se de ler este tópico antes de configurar seu ambiente do Cloud Connector. Quando estiver pronto para implantar e configurar o Cloud Connector Edition, consulte [configurar e gerenciar o Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

O Cloud Connector Edition 2,1 já está disponível. Se você ainda não tiver atualizado para 2,1, consulte [upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Você pode encontrar o arquivo de instalação em [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> A Microsoft dá suporte à versão anterior do Cloud Connector Edition por 60 dias após o lançamento de uma nova versão. A Microsoft dará suporte à versão 2.0.1 por 60 dias após o lançamento de 2,1 para permitir a atualização. Não há mais suporte para todas as versões anteriores à versão 2.0.1.

O Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de máquinas virtuais (VMs) empacotadas que implementam a conectividade PSTN local com o sistema de telefonia. Ao implantar uma topologia mínima do Skype for Business Server em um ambiente virtualizado, os usuários em sua organização que estão hospedados na nuvem podem receber serviços PBX da nuvem da Microsoft, mas a conectividade PSTN é fornecida por meio da infraestrutura de voz local existente.

![Diagrama de topologia mostrando o Cloud PBX gateway conectando o Cloud PBX a uma implantação local do Skype for Business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Como o Cloud Connector permite que você integre os serviços de sistema de telefonia com seu ambiente de telefonia existente — por exemplo, PBX, dispositivos analógicos e centros de chamadas, você pode implementar uma migração em fases da sua solução de telefonia existente para o sistema de telefonia.

Por exemplo, suponha que sua empresa tenha um Call Center sofisticado com funcionalidade específica que o sistema de telefonia não fornece. Você pode optar por deixar os usuários do Call Center com a solução existente, mas mover outros usuários para o sistema de telefonia.

O Cloud Connector fornecerá o roteamento entre os usuários hospedados no local e online, e você pode optar por usar seu próprio provedor de PSTN com o sistema de telefonia.

Considere o seguinte ao planejar sua implantação do Cloud Connector Edition:

- Para usar o Cloud Connector para aproveitar as vantagens das soluções de voz em nuvem, você precisará se inscrever para uma organização do Microsoft 365 ou do Office 365 que inclua o sistema de telefonia. Se você ainda não tiver uma organização do Microsoft 365 ou do Office 365, poderá saber como se inscrever aqui: [Microsoft 365 para empresas](https://products.office.com/business/office). Observe que você precisará se inscrever para um plano que inclua o Skype for Business online.

- Para registrar dispositivos do Cloud Connector com o serviço do Skype for Business Online e para executar vários cmdlets, o Cloud Connector 2,0 e posterior requer uma conta dedicada do Microsoft 365 ou do Office 365 com os direitos de administrador locatário do Skype for Business. As versões anteriores à 2,0 do Cloud Connector exigem uma conta dedicada do Microsoft 365 ou do Office 365 com direitos de administrador global do locatário.

- O Cloud Connector não requer uma implantação completa do Skype for Business Server.

    No momento, o Cloud Connector não pode coexistir com os servidores locais do Lync ou do Skype for Business. Se você deseja mover os usuários existentes do Lync ou do Skype for Business para o Microsoft 365 e manter a telefonia local para seus usuários, considere o sistema de telefonia com conectividade local usando uma implantação existente do Skype for Business Server. Para saber mais, confira [planejar sua solução de sistema de telefonia (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md) e [planejar o sistema de telefonia com conectividade PSTN local no Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se você tiver uma implantação anterior do Skype for Business ou do Lync Server e estendir o esquema, não será necessário limpar o esquema para a implantação do Cloud Connector, desde que você tenha removido todos os componentes do Skype for Business ou do Lync Server do seu ambiente.

- Seus usuários estão hospedados online.

- Se sua organização configurou a sincronização de diretórios (DirSync), todas as contas de usuários planejados para voz híbrida devem ser criadas primeiro na implantação local e, em seguida, sincronizadas com a nuvem.

- Você pode manter sua operadora PSTN atual, se necessário.

- Se você deseja fornecer conferência discada para os usuários hospedados no Cloud Connector, é possível adquirir a licença de conferência PSTN ou o pagamento à medida que a conferência de áudio é oferecida pela Microsoft.

- A licença de audioconferência (ou oferta de pagamento à medida que você passa) também é necessária para escalonamentos de chamadas. Se um usuário do Skype for Business receber uma chamada de um usuário PSTN externo e quiser adicionar mais um participante a essa chamada (escalonar a chamada para uma conferência), o escalonamento será executado através do serviço de conferência de áudio da Microsoft.

- O Cloud Connector 2,0 e versões posteriores agora dão suporte a bypass de mídia. O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (rede telefônica pública comutada), um gateway ou um SBC (controlador de borda da sessão), e elimine o componente do Cloud Connector Edition do caminho da mídia. Para obter mais informações, consulte [Plan for Media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- O Cloud Connector 2,1 e posterior suporta o monitoramento do Cloud Connector usando o Operations Management Suite (OMS). Para obter mais informações, consulte [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- O Cloud Connector está disponível em todos os países onde o Office 365 Enterprise E5 está disponível.

Este tópico contém as seguintes seções:

- [Componentes do Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologias da edição do Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisitos para implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informações que você precisa coletar antes da implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerações do plano de discagem](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerações sobre alta disponibilidade](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Fluxo de mídia do Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoramento e solução de problemas](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Para saber mais](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componentes do Cloud Connector Edition
<a name="BKMK_Components"> </a>

Com o Cloud Connector Edition, você implanta um conjunto de VMs empacotadas que contêm uma topologia mínima do Skype for Business Server, consistindo em um componente de borda, um componente de mediação e uma função de repositório de gerenciamento central (CMS). Você também instalará um controlador de domínio, que é necessário para o funcionamento interno do Cloud Connector. Esses serviços são configurados para o híbrido com sua organização do Microsoft 365 ou do Office 365 que inclui o Skype for Business Online Services.

![Componentes do Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Os componentes do Cloud Connector fornecem a seguinte funcionalidade:

- **Componente de borda** – a comunicação entre a topologia local e os serviços online passa pelo componente de borda, que inclui os seguintes componentes:

  - **Borda de acesso** : fornece roteamento SIP entre a implantação local e o Skype for Business online.

  - **Media Relay** : fornece roteamento de mídia entre o componente de mediação e outros pontos de extremidade de mídia.

  - **Autenticação de retransmissão de mídia/MRAS** -gera tokens para acesso ao Media Relay.

- **Roteamento de saída** – fornece balanceamento de carga do tráfego de voz entre gateways ou SBCS conectado a um dispositivo do Cloud Connector. As chamadas serão divididas igualmente entre todos os gateways ou SBCs conectados ao dispositivo do Cloud Connector.

    Fornece roteamento para gateways com base em políticas. Só há suporte para políticas globais baseadas em números PSTN de destino (saída).

- **Função de repositório de gerenciamento central (CMS)** – inclui o repositório de configuração para os componentes de topologia, incluindo a transferência de arquivos CMS.

- **Réplica do repositório de gerenciamento central (CMS)** – sincroniza informações de configuração do banco de dados global do CMS no servidor de função CMS.

- **Controlador de domínio** -serviços de domínio do Active Directory do Cloud Connector para armazenar todas as configurações globais e grupos necessários para implantar componentes do Cloud Connector. Uma floresta será criada para cada dispositivo do Cloud Connector. O controlador de domínio não deve ter conexões com o Active Directory de produção. Os serviços do Active Directory incluem:

  - Serviços de Domínio do Active Directory

  - Serviços de certificados do Active Directory para emitir certificados internos

- **Componente de mediação** -implementa o protocolo de mapeamento SIP e Media Gateway entre o Skype for Business e gateways PSTN. Inclui uma réplica de CMS que sincroniza a configuração do banco de dados CMS global.

## <a name="cloud-connector-edition-topologies"></a>Topologias da edição do Cloud Connector
<a name="BKMK_Topologies"> </a>

Para os fins desta discussão, vamos nos referir a sites PSTN. Um site PSTN é uma combinação de dispositivos do Cloud Connector, implantado no mesmo local e com gateways PSTN comuns conectados a eles. Os sites PSTN permitem:

- Fornecer conectividade aos gateways mais próximos aos seus usuários.

- Permitir escalabilidade com a implantação de vários dispositivos do Cloud Connector em um ou mais sites PSTN.

- Permitir alta disponibilidade implantando vários dispositivos do Cloud Connector em um único site PSTN.

Este tópico introduz sites PSTN. Para obter mais informações sobre como planejar seus sites PSTN, consulte [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Você pode implantar as seguintes topologias do Cloud Connector:

- Um único dispositivo do Cloud Connector Edition por site PSTN. Essa topologia é recomendada para fins de avaliação somente porque não oferece alta disponibilidade.

- Vários dispositivos do Cloud Connector Edition por site PSTN para fornecer alta disponibilidade.

- Vários sites PSTN com vários dispositivos do Cloud Connector Edition para fornecer escalabilidade com alta disponibilidade. Você pode implantar até 200 sites.

Ao planejar sua topologia, considere o seguinte:

- Com o Cloud Connector 2,0 e posterior, um site PSTN pode ter até 16 dispositivos do Cloud Connector. As versões anteriores dão suporte a até 4 dispositivos por site.

- Há dois tipos de configurações de hardware testadas com o Cloud Connector:

  - A versão maior é capaz de lidar com grandes volumes de chamadas simultâneas e é compatível com todos os tipos de ambientes de produção.

  - A versão menor deve ser executada em hardware de extremidade inferior e pode ser usada para fins de avaliação ou para sites com baixos volumes de chamadas. Se você implantar uma versão menor do Cloud Connector, ainda precisará ficar atento aos requisitos de hardware de classe de produção (como fontes de alimentação duplas).

- Se você tiver a versão 2,0 ou posterior do Cloud Connector e implantar a configuração máxima de 16 dispositivos (com hardware maior), o seu site PSTN poderá lidar com até 8.000 chamadas simultâneas. Se você implantar a versão menor, o limite com suporte é 800.

    Você também precisa dedicar alguns dispositivos para alta disponibilidade. A recomendação mínima é que um dispositivo deve ser reservado para alta disponibilidade.

  - Com a versão 2, se você implantar uma configuração de 15 + 1, seu local de PSTN poderá lidar com até 7.500 chamadas simultâneas.

  - Se você tiver uma versão anterior e implantar a configuração máxima de 3 + 1 (com hardware maior), o seu site PSTN poderá lidar com até 1500 chamadas simultâneas. Se você implantar a versão menor, o limite com suporte é 150.

-  Se você precisar de mais chamadas por site PSTN, você pode expandir ao implantar sites PSTN adicionais no mesmo local.

> [!NOTE]
> A menos que indicado, os diagramas e os exemplos abaixo pressupõem o uso da versão maior do Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Único dispositivo do Cloud Connector em um único site PSTN

O diagrama a seguir mostra um único dispositivo do Cloud Connector Edition em um único site PSTN. Observe que o Cloud Connector consiste em quatro VMs instaladas em um computador host físico que está dentro de uma rede de perímetro para fins de segurança.

![Um conector de nuvem com um site PSTN](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Vários dispositivos do Cloud Connector em um único site PSTN

 Para fins de escalabilidade e alta disponibilidade, você pode optar por ter várias edições do Cloud Connector em um único site PSTN, conforme mostrado no diagrama a seguir. Considere o seguinte:

- As chamadas são distribuídas em ordem aleatória entre os conectores de nuvem em um pool.

- Para fins de planejamento de capacidade, você deve considerar a capacidade de lidar com a carga se um ou mais conectores de nuvem estiverem offline, com base nos seguintes cálculos:

  - **N + 1 caixas.** Para a versão maior do Cloud Connector, N + 1 caixas suportam 500 \* N chamadas simultâneas com disponibilidade de 99,8%.

    Para a versão menor do Cloud Connector, N + 1 caixas suportam 50 \* N chamadas simultâneas com disponibilidade de 99,8%.

  - **N + 2 caixas.** Para a versão maior do Cloud Connector, N + 2 caixas suportam 500 \* N chamadas simultâneas com disponibilidade de 99,9%.

    Para a versão menor do Cloud Connector, N + 2 caixas suportam 50 \* N chamadas simultâneas com disponibilidade de 99,9%.

![Dois conectores de nuvem dentro de um site PSTN](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Vários sites PSTN com um ou mais conectores de nuvem por site

Você também pode optar por ter vários sites PSTN com uma ou mais edições do Cloud Connector em cada site. Se o seu site PSTN atingir o limite de chamadas simultâneas, você poderá adicionar outro site PSTN para lidar com a carga.

Vários sites PSTN também permitem que você forneça conectividade aos gateways mais próximos aos seus usuários. Por exemplo, suponha que você tenha gateways PSTN em Seattle e Amsterdã. Você pode implantar dois sites PSTN, um em Seattle, um em Amsterdã — e atribuir usuários para usar o site PSTN mais próximo. Os usuários de Seattle serão roteados para o site e os gateways PSTN de Seattle, enquanto os usuários no Amsterdã serão roteados para o site PSTN e gateways da Amsterdã:

![Cloud Connector Edition dentro de dois sites PSTN](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisitos para implantação
<a name="BKMK_Requirements"> </a>

Antes de implantar o Cloud Connector Edition, verifique se você tem o seguinte para seu ambiente:

- **Para o computador host-** As VMs do Cloud Connector devem ser implantadas em hardware dedicado executando o Windows Server 2012 R2 Datacenter Edition (inglês) com a função Hyper-V habilitada.

    Para a versão 2,0 e posterior, a placa de rede do computador host associada à opção corpnet do Skype for Business deve ter um endereço IP configurado na mesma sub-rede que as máquinas da rede corporativa do Cloud Connector.

- Para as versões 2,1 e posteriores, o dispositivo host deve ter o .NET Framework 4.6.1 ou posterior instalado.

- **Para as máquinas virtuais-** Uma imagem ISO (. ISO) do Windows Server 2012 R2 (inglês). O ISO será convertido em VHDs para as máquinas virtuais que executarão o Skype for Business Cloud Connector Edition.

- O hardware necessário para dar suporte à instalação das quatro VMs para cada edição do Cloud Connector em sua implantação. As seguintes configurações são recomendadas:

  - processador dual de 64 bits, seis principais (12 núcleos reais), 2,50 gigahertz (GHz) ou superior

  - 64 gigabytes (GB) de RAM ECC

  - 4 600 GB (ou mais) 10K RPM 128M cache 6Gbps discos SAS, configurados em uma configuração RAID 5

  - Três adaptadores de rede de alta velocidade RJ45 de 1 Gbps

- Se você optar por implantar a versão menor do Cloud Connector Edition que oferece suporte a até 50 chamadas simultâneas, será necessário o seguinte hardware:

  - Intel i7 4790 quad core com Intel 4600 Graphics (não é necessário ter gráficos de alta extremidade)

  - 32 GB DDR3-1600 não ECC

  - 2:1 TB 7200RPM SATA III (6 Gbps) no RAID 0

  - Ethernet de 2:1 Gbps (RJ45)

- Se um servidor proxy for necessário no computador host para navegar na Internet, você deverá fazer as seguintes alterações de configuração:

  - Para ignorar o proxy, especifique as configurações de proxy WinHTTP definidas com o servidor proxy e uma lista de bypass, incluindo o "192.168.213 \* ". rede usada pelos serviços de gerenciamento do Cloud Connector e pela sub-rede do Skype for Business corpnet conforme definido no arquivo CloudConnector. ini. Caso contrário, a conectividade de gerenciamento falhará e impedirá a implantação e a recuperação automática do Cloud Connector. Veja a seguir um exemplo de comando de configuração WinHTTP: netsh WinHTTP Set proxy "10.10.10.175:8080" bypass-List = " \* . local; 1. \* ; 172,20. \* ; 192.168.218. \* ' \< local \> ".

  - Especifique as configurações de proxy por máquina, em vez de por usuário. Caso contrário, os downloads do Cloud Connector falharão. Você pode especificar as configurações de proxy por máquina com uma alteração de registro ou com a configuração de política de grupo da seguinte maneira:

  - **Registro:** HKEY_LOCAL_MACHINE configurações de \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Política de Grupo:** \>Modelos administrativos do computador \> componentes do Windows \> Internet Explorer: definir configurações de proxy por máquina (não por usuário)

- PBX/tronco qualificado ou SBC/gateway qualificado (é recomendável um mínimo de dois gateways).

    O Cloud Connector oferece suporte aos mesmos controladores de borda de sessão (SBCs) certificados para o Skype for Business. Para obter mais informações, consulte [infraestrutura de telefonia para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Uma conta de administrador de servidor local com permissões para instalar e configurar o Hyper-V nos servidores host. A conta deve ter permissões de administrador no servidor local onde o Hyper-V está instalado e configurado.

- Durante a implantação, você será solicitado a criar uma conta de administrador de domínio com permissões para criar e publicar a topologia no domínio do Cloud Connector.

- Os registros DNS externos, que são definidos no arquivo CloudConnector. ini incluído no pacote de instalação:

  - Registro DNS externo para serviço de borda de acesso do componente de borda; por exemplo, AP. \< Nome do domínio \> . Você precisa de um registro por site PSTN. Esse registro deve conter endereços IP de todas as bordas desse site.

- Uma organização do Microsoft 365 ou do Office 365 com todos os registros DNS e SRV necessários criados.

    > [!IMPORTANT]
    > Quando você integra seu locatário ao Cloud Connector Edition, não há suporte para o uso do sufixo de domínio padrão,. onmicrosoft.com, como um domínio SIP para sua organização. > não é possível usar SIP. \< Nome \> do domínio como o nome da interface de proxy de acesso de borda do Cloud Connector, pois esse registro DNS é usado pelo Microsoft 365 e pelo Office 365.

- Um certificado para a borda externa Obtida de uma autoridade de certificação pública (AC).

- As regras de firewall para permitir o tráfego por meio das portas necessárias foram concluídas.

- Uma conexão com a Internet para o computador host e as VMs. O Cloud Connector baixa alguns softwares da Internet; Portanto, você deve fornecer informações de gateway e de servidor DNS para que a máquina host do Cloud Connector e as VMs possam se conectar à Internet e baixar o software necessário.

- Um módulo PowerShell remoto do locatário instalado no computador host.

- As credenciais de administrador do Skype for Business para executar o PowerShell remoto.

    > [!IMPORTANT]
    > A conta de administrador não deve ter a autenticação multifator habilitada.

> [!NOTE]
> A implantação do Cloud Connector só é suportada na plataforma virtual do Microsoft Hyper-V. Outras plataformas, como VMware e Amazon Web Services, não são suportadas.

> [!NOTE]
> A orientação de hardware mínima para executar o Cloud Connector é baseada na capacidade básica de hardware (núcleos, MHz, gigabytes e assim por diante) com algum buffer para acomodar deficiências de desempenho intangíveis enterradas na arquitetura de qualquer computador. A Microsoft executou o pior caso de teste de carga na reunião de hardware disponível no mercado para obter as diretrizes mínimas. A qualidade da mídia e o desempenho do sistema são verificados. Parceiros oficiais de dispositivos do Cloud Connector da Microsoft têm implementações de hardware do conector de nuvem específico nas quais eles têm desempenho de forma independente e são de acordo com a adequação do seu hardware para atender aos requisitos de carga e qualidade.

> [!NOTE]
> Os dispositivos produzidos pelo AudioCodes e pelo Sonus modificaram o código e são executados no Windows Server Standard Edition de servidores. Há suporte para esses dispositivos.

## <a name="information-you-need-to-gather-before-deployment"></a>Informações que você precisa coletar antes da implantação
<a name="BKMK_PlanDeployment"> </a>

Antes de começar sua implantação, você precisa determinar o tamanho da sua implantação, os domínios SIP que estão sendo atendidos e as informações de configuração para cada site PSTN que planeja implantar. Para começar, você irá:

- Identificar todos os domínios SIP que serão atendidos por essa implantação com base nos URIs SIP em uso na sua empresa.

- Determine o número de sites PSTN que você precisa implantar.

- Verifique se você tem o hardware necessário para dar suporte às quatro VMs que instalará para cada edição do Cloud Connector.

Para cada site PSTN que você planeja implantar, você precisa:

- Criar nomes para todos os componentes em cada dispositivo do Cloud Connector (consulte [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definir intervalos de porta (consulte [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Criar registros DNS externos para o componente de borda (veja [requisitos para implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinar os requisitos de certificado para o componente de borda (veja [requisitos de certificado](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Portas e protocolos
<a name="BKMB_Ports"> </a>

Ao definir intervalos de porta de mídia, esteja ciente do seguinte:

- Os clientes sempre usam o intervalo de porta 50000 a 50019 para tráfego de mídia — esse intervalo é predefinido no Skype for Business Online e não pode ser alterado.

- Por padrão, o componente de mediação usará o intervalo de porta 49 152 a 57 500 para o tráfego de mídia. No entanto, a conexão é estabelecida por meio do firewall interno e, por motivos de segurança, você pode limitar esse intervalo de porta em sua topologia. Você precisará de até 4 portas por chamada. Se quiser limitar o número de portas entre o componente de mediação e o gateway PSTN, você também precisará configurar o intervalo de porta correspondente no gateway.

- Você deve implantar o Cloud Connector em uma rede de perímetro. Isso significa que você terá dois firewalls:

  - O primeiro firewall é externo entre a Internet e sua rede de perímetro.

  - O segundo firewall é interno entre a rede de perímetro e sua rede interna.

    Os clientes podem estar na Internet ou na rede interna:

  - Os clientes na Internet se conectarão à PSTN por meio do firewall externo por meio do componente de borda.

  - Os clientes na rede interna serão conectados por meio do firewall interno ao componente de mediação na rede de perímetro, que conectará o tráfego ao SBC ou ao gateway PSTN.

    Isso significa que você precisa abrir as portas em ambos os firewalls.

As tabelas a seguir descrevem as portas e os intervalos de portas para os firewalls externos e internos.

Esta tabela mostra as portas e os intervalos de portas para habilitar a comunicação entre os clientes na rede interna e o componente de mediação:

**Firewall interno**



|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Componente de mediação do Cloud Connector  <br/> |SBC/gateway PSTN  <br/> |Qualquer tamanho  <br/> |TCP 5060\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente de mediação do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP 5068/TLS 5067  <br/> |
|Componente de mediação do Cloud Connector  <br/> |SBC/gateway PSTN  <br/> |UDP 49 152-57 500  <br/> |Haja\*\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente de mediação do Cloud Connector  <br/> |Haja\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Componente de mediação do Cloud Connector  <br/> |Clientes internos  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/> Opcion  <br/> |
|Componente de mediação do Cloud Connector  <br/> |Clientes internos  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|Clientes internos  <br/> |Componente de mediação do Cloud Connector  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clientes internos  <br/> |Componente de mediação do Cloud Connector  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Este é o intervalo de portas padrão no componente de mediação. Para o fluxo de chamadas ideal, são necessárias quatro portas por chamada.

\*\*Essa porta deve ser configurada no SBC/gateway PSTN; 5060 é um exemplo. Você pode configurar outras portas no seu gateway SBC/PSTN.

\*\*\*Observe que você também pode limitar o intervalo de porta em seu SBC/gateway, se permitido pelo fabricante de SBC/gateway.

Para fins de segurança, é possível limitar o intervalo de porta para o componente de mediação usando o cmdlet [set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Por exemplo, o seguinte comando limita o número de portas que o componente de mediação usará para o tráfego de mídia como 50 000-51 000 para áudio (entrada e saída). O componente de mediação poderá lidar com as chamadas simultâneas 250 com essa configuração. Observe que você também pode querer limitar esse intervalo no SBC/gateway PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Para recuperar o nome do componente de mediação e ver as portas padrão, você pode usar o cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) da seguinte maneira:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

A tabela a seguir mostra as portas e os intervalos de portas para habilitar a comunicação entre o componente de borda do Cloud Connector para o firewall externo. Esta tabela mostra uma recomendação mínima.

Nesse caso, todo o tráfego de mídia para a Internet fluirá por meio da borda online da seguinte maneira: ponto de extremidade do usuário – borda \> online-- \> borda do conector de nuvem:

**Firewall externo-configuração mínima**



|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP 80  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |UDP 53  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP 53  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |

A próxima tabela mostra as portas e os intervalos de portas para habilitar a comunicação entre o componente de borda do Cloud Connector para o firewall externo. Esta tabela mostra a solução recomendada.

Nesse caso, todo o tráfego de mídia para o ponto de extremidade na Internet pode fluir diretamente para o componente de borda do Cloud Connector. O caminho de mídia será a borda do conector de nuvem do ponto de extremidade do usuário \> .

> [!NOTE]
> Essa solução não funcionará se o ponto de extremidade do usuário estiver protegido por um NAT simétrico.

**Firewall externo – configuração recomendada**


|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP 80  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |UDP 53  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |Qualquer tamanho  <br/> |TCP 53  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP 50000-59.999  <br/> |Qualquer tamanho  <br/> |
|Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |UDP 3478; UDP 50000-59.999  <br/> |Qualquer tamanho  <br/> |
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |TCP 443; TCP 50000-59.999  <br/> |
|Qualquer tamanho  <br/> |Interface externa de borda do Cloud Connector  <br/> |Qualquer tamanho  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisitos de conectividade com a Internet do host
<a name="BKMB_Ports"> </a>

O computador host deve ser capaz de acessar recursos externos para instalar, atualizar e gerenciar o Cloud Connector com êxito. A tabela a seguir mostra os destinos e as portas necessários entre o computador host e os recursos externos.

|Direção  <br/> |IP de origem  <br/> |IP de destino  <br/> |Porta de origem  <br/> |Porta de destino  <br/> |Protocolo  <br/> |Propósito  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Saída  <br/> |IPs do host do Cloud Connector  <br/> |qualquer  <br/> |qualquer  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Saída  <br/> |IPs do host do Cloud Connector  <br/> |qualquer  <br/> |qualquer  <br/> |80, 443  <br/> |TCP  <br/> |CRL (lista de certificados revogados)  <br/> |
|Saída  <br/> |IPs do host do Cloud Connector  <br/> |qualquer  <br/> |qualquer  <br/> |80, 443  <br/> |TCP  <br/> |Atualização do Cloud Connector  <br/> Skype for Business Online  <br/> PowerShell de administração  <br/> Windows Update  <br/> |

Se forem necessárias regras mais restritivas, consulte as seguintes URLs de lista branca:

- [URLs da lista de certificados revogados](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) nas [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [como configurar um firewall para atualizações de software](https://technet.microsoft.com/library/bb693717.aspx)

- PowerShell de administração do Skype for Business Online: \* . online.Lync.com

    Se você precisar de uma exclusão de proxy para esse destino, será necessário adicioná-lo à lista de bypass do WinHTTP.

- Atualização do Cloud Connector: [centro de download](https://aka.ms/CloudConnectorInstaller), [https://go.microsoft.com](https://go.microsoft.com) e[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Resolução de nomes DNS para o componente de borda
<a name="BKMB_Ports"> </a>

O componente de borda precisa resolver os nomes externos dos serviços do Microsoft 365 ou do Office 365 e os nomes internos de outros componentes do Cloud Connector.

Cada componente de borda é um computador multihomed com interfaces opostas externas e internas. O Cloud Connector implanta servidores DNS no componente do controlador de domínio dentro da rede de perímetro. Você pode apontar o servidor de borda para o servidor DNS no perímetro de todas as resoluções de nome, mas precisa habilitar o servidor DNS do Cloud Connector para resolver nomes externos, configurando uma zona DNS contendo um ou mais registros DNS A para consultas externas que fazem referência a outros servidores DNS públicos.

No arquivo. ini, se você definir o nome FQDN dos gateways do mesmo espaço de domínio que o domínio SIP, a zona autoritativa desse domínio SIP será criada no servidor DNS dentro do perímetro. Se o servidor de borda for apontado para este servidor DNS para resolver nomes, a borda nunca resolverá o _sipfederationtls. \< seudomínio \> registro DNS, que é necessário para o fluxo de chamadas. Nesse caso, a Microsoft recomenda que você forneça um servidor DNS na interface externa de borda para resolver pesquisas de nome de Internet e cada componente de borda deve usar um arquivo HOST para resolver outros nomes de componente do Cloud Connector para endereços IP.

> [!NOTE]
> Por motivos de segurança, recomendamos que você não aponte o servidor DNS do Cloud Connector para servidores internos no domínio de produção para resolução de nomes.

### <a name="determine-deployment-parameters"></a>Determinar parâmetros de implantação
<a name="BKMK_SiteParams"> </a>

Primeiro, você precisa definir os seguintes parâmetros de implantação comuns:


|**Item**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Domínios SIP  <br/> |URI do SIP em uso pelos usuários da empresa. Forneça todos os domínios SIP que serão atendidos por essa implantação. Você pode ter mais de um domínio SIP.  <br/> ||
|Número de sites PSTN  <br/> |O número de sites PSTN que você vai implantar.  <br/> ||

Para cada site PSTN que você planeja implantar, será necessário coletar as seguintes informações antes de iniciar a implantação. Você precisará fornecer essas informações ao atualizar o arquivo CloudConnector. ini.

Ao configurar informações de gateway, lembre-se do seguinte:

- Se você tiver apenas um gateway, remova a seção no arquivo. ini do segundo gateway. Se houver mais de dois gateways, siga o formato existente para adicionar novos.

- Certifique-se de que o endereço IP e a porta do (s) gateway (s) estão corretos.

- Para dar suporte à alta disponibilidade no nível do gateway PSTN, mantenha o gateway secundário ou adicione gateways adicionais.

Opcion Para restringir os números de chamada de saída, atualize o valor LocalRoute.



|**Parâmetros de site**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Nome do domínio da máquina virtual  <br/> |Nome do domínio para os componentes internos do Cloud Connector. Esse domínio deve ser diferente do domínio de produção. O nome deve ser o mesmo em todos os dispositivos do Cloud Connector.  <br/> Nome no arquivo. ini: "VirtualMachineDomain"  <br/> |. o domínio local é o preferencial.  <br/> |
|Nome do controlador de domínio do Cloud Connector  <br/> |Nome do controlador de domínio.  <br/> Nome no arquivo. ini: "servername"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|Máscara de sub-rede/IP do controlador de domínio do Cloud Connector  <br/> |Endereço IP do controlador de domínio.  <br/> Nome no arquivo. ini: "IP"  <br/> ||
|FQDNs do serviço online do Microsoft 365 ou do Office 365  <br/> |Deve ser o padrão na maioria dos casos para a instância do Microsoft 365 ou do Office 365 em todo o mundo.  <br/> Nome no arquivo. ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nome do site do Skype for Business; por exemplo, Seattle.  <br/> Nome no arquivo. ini: "SiteName"  <br/> Para a versão 1.4.1 e posterior, o nome do site deve ser diferente para cada site, e o nome deve corresponder ao site PSTN, se ele existir, definido no Microsoft 365 ou no Office 365. Observe que os sites PSTN serão criados automaticamente ao registrar o primeiro dispositivo em um site.  <br/> ||
|HardwareType  <br/> Versão 1.4.1 e posterior  <br/> |Tipo de hardware. O valor padrão é Normal. Você também pode definir como mínimo.  <br/> ||
|Código do País  <br/> |Código do país para discagem.  <br/> Nome no arquivo. ini: "CountryCode"  <br/> ||
|Cidade  <br/> |Cidade (opcional).  <br/> Nome no arquivo. ini: "cidade"  <br/> ||
|Estado  <br/> |Estado (opcional).  <br/> Nome no arquivo. ini: "estado"  <br/> ||
|Endereço IP da VM base  <br/> |O endereço IP da VM de base temporária que será usado para criar o VHDX para todas as máquinas virtuais do Cloud Connector. Esse IP deve estar na mesma sub-rede da rede corporativa de perímetro definida na próxima etapa e requer acesso à Internet. Certifique-se de definir o gateway padrão corporativo e o DNS que é roteável para a Internet.  <br/> Nome no arquivo. ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> Wsusserver  <br/> Versão 1.4.1 e posterior  <br/> |O endereço do Windows Server Update Services (WSUS) — um servidor de intranet para hospedar atualizações do Microsoft Update.  <br/> Você pode deixar em branco se o WSUS não for necessário.  <br/> ||
|Máscara de sub-rede para rede interna  <br/> |O Cloud Connector configura uma rede IP para comunicação interna entre componentes do Cloud Connector. A borda também deve estar conectada a outra sub-rede que permita a conectividade com a Internet.  <br/> Nome no arquivo. ini: "CorpnetIPPrefixLength" em "parâmetros de um pool de rede VM"  <br/> ||
|Máscara de sub-rede para rede externa  <br/> |Para a rede externa do componente de borda.  <br/> Nome no arquivo. ini: "InternetIPPrefix" em "parâmetros de um pool de rede VM"  <br/> ||
|Nome do comutador para rede interna  <br/> |Nome para o comutador que será usado para a rede interna do Cloud Connector.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "CorpnetSwitchName" em "parâmetros de um pool de rede VM"  <br/> ||
|Nome do comutador para rede externa  <br/> |Nome para o comutador que será usado para a rede externa do Cloud Connector.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "InternetSwitchName" em "parâmetros de um pool de rede VM"  <br/> ||
|Gateway padrão para rede interna  <br/> |Esse gateway deve fornecer acesso à Internet (a Internet também requer a configuração do servidor DNS) e será configurado em interfaces internas de componentes do Cloud Connector.  <br/> Nome no arquivo. ini: "CorpnetDefaultGateway" em "parâmetros de um pool de rede VM"  <br/> ||
|Gateway padrão para interface externa do componente de borda  <br/> |Será configurado na interface externa do componente de borda.  <br/> Nome no arquivo. ini: "InternetDefaultGateway" em "parâmetros de um pool de rede VM"  <br/> ||
|Servidor DNS para rede interna  <br/> |Será configurado na interface interna da VM temporária. Deve fornecer resolução de nome para nomes da Internet. Sem fornecer um servidor DNS, a conexão com a Internet falhará e a implantação não será concluída.  <br/> Nome no arquivo. ini: "CorpnetDNSIPAddress" em "parâmetros de um pool de rede VM"  <br/> ||
|Servidor DNS para interface externa do componente de borda  <br/> |Será configurado na interface externa da borda.  <br/> Nome no arquivo. ini: "InternetDNSIPAddress" em "parâmetros de um pool de rede VM"  <br/> ||
|Nome do comutador de gerenciamento  <br/> |O switch de gerenciamento é um comutador temporário que será criado automaticamente e que será usado para a configuração do Cloud Connector durante a implantação. Ele será desconectado automaticamente após a implantação. Deve ser uma sub-rede diferente de outras redes usadas no Cloud Connector.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "ManagementSwitchName" em "parâmetros de um pool de rede VM"  <br/> ||
|Endereço de sub-rede de gerenciamento/máscara de sub-rede  <br/> |A sub-rede de gerenciamento é uma sub-rede temporária que será criada automaticamente e que será usada para a configuração do Cloud Connector durante a implantação. Ele será removido automaticamente após a implantação. Deve ser uma sub-rede diferente de outras redes usadas no Cloud Connector.  <br/> Nomes no arquivo. ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" em "parâmetros de um pool de rede VM  <br/> ||
|Máquina do repositório de gerenciamento central (CMS)  <br/> |FQDN único usado para o repositório de gerenciamento central (CMS). O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "servername" em "parâmetros do serviço de gerenciamento central primário"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> (Nome do pool CMS = nome do servidor)  <br/> |
|Endereço IP do computador CMS  <br/> |Endereço IP para servidor CMS (interno na rede de perímetro).  <br/> Nome no arquivo INI: "IP" em "parâmetros do serviço de gerenciamento central primário"  <br/> ||
|Nome do compartilhamento de arquivo  <br/> |Nome do compartilhamento de arquivo a ser criado no servidor CMS para dados de replicação do Skype for Business (por exemplo, CmsFileStore).  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "CmsFileStore" em "parâmetros do serviço de gerenciamento central primário"  <br/> ||
|Nome do pool do componente de mediação  <br/> |Nome do pool do componente de mediação. Insira somente o nome NetBIOS. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "PoolName" em "parâmetros de um pool de servidores de mediação"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|Nome do componente de mediação  <br/> |Nome do componente do componente de mediação 1. Insira somente o nome NetBIOS. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "servername" em "parâmetros de um pool de servidores de mediação"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|Endereço IP do computador do componente de mediação  <br/> |IP interno do corpnet para o componente de mediação (interno na rede de perímetro).  <br/> Nome no arquivo. ini: "IP" em "parâmetros de um pool de servidores de mediação"  <br/> ||
|Nome interno do pool de borda  <br/> |Nome do pool do componente de borda. Insira somente o nome NetBIOS. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "InternalPoolName" em "parâmetros de um pool de servidores de borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|Nome interno do servidor de borda  <br/> |Nome do componente do componente de borda. Insira somente o nome NetBIOS. O nome de domínio do AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "InternalServerName" em "parâmetros de um pool de servidores de borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|IP interno do servidor de borda  <br/> |IP de rede de perímetro interna do componente de borda para se comunicar com outros componentes do Cloud Connector.  <br/> Nome no arquivo. ini: "InternalServerIPs" em "parâmetros de um pool de servidores de borda"  <br/> ||
|Nome externo do pool de acesso  <br/> |Nome da borda de acesso; por exemplo, AP. Esse nome deve corresponder ao nome fornecido para o certificado SSL. Insira somente o nome NetBIOS. O nome de domínio SIP será usado para gerar o FQDN. Um nome de pool externo será usado para todos os componentes de borda no pool. Um pool de acesso de borda é necessário para cada site PSTN.  <br/> Nome no arquivo. ini: "ExternalSIPPoolName" em "parâmetros de um pool de servidores de borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> "SIP" é reservado e, portanto, não pode ser usado como o nome.  <br/> O nome FQDN gerado deve corresponder ao nome fornecido para o certificado SSL.  <br/> |
|IP externo de borda de acesso  <br/> |IP externo do componente de Borda – IP público se não houver NAT disponível ou IP convertido (especifique ambos os endereços se mapeado).  <br/> Nome no arquivo. ini: "ExternalSIPIPs" em "parâmetros de um pool de servidores de borda"  <br/> ||
|Nome de retransmissão de mídia  <br/> |Nome da borda de retransmissão de mídia de vídeo de áudio; por exemplo, Sr. Um nome de pool externo será usado para todos os componentes de borda em um pool. É necessário um pool de retransmissão de mídia de borda por site PSTN.  <br/> Nome no arquivo. ini: "ExternalMRFQDNPoolName" em "parâmetros de um pool de servidores de borda"  <br/> |Deve ter 15 caracteres ou menos. Insira somente o nome NetBIOS.  <br/> |
|IP externo da borda de retransmissão de mídia  <br/> |Atualmente, somente um IP tem suporte, portanto, ele será o mesmo IP que a borda de acesso, público ou IP mapeado (especifique ambos os endereços se mapeado). Pode ser o mesmo endereço que o IP externo da borda de acesso do componente de borda. Observação se a borda estiver por trás do NAT, você também precisará especificar o valor para o próximo parâmetro.  <br/> Nome no arquivo. ini: "ExternalMRIPs" em "parâmetros de um pool de servidores de borda"  <br/> ||
|IP externo da borda de retransmissão de mídia (se a borda estiver atrás de NAT)  <br/> |Se sua borda estiver atrás de NAT, você também precisará especificar o endereço público do dispositivo NAT.  <br/> Nome no arquivo. ini: "ExternalMRPublicIPs" em "parâmetros de um pool de servidores de borda"  <br/> ||
|Marca e modelo do gateway de voz 1  <br/> |Especifique a marca e o modelo do SBC/gateway de voz. Observe que é possível conectar um dispositivo ou tronco SIP da lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Marca e modelo do gateway de voz 2 (Copie essa linha se tiver mais de dois gateways)  <br/> |Especifique a marca e o modelo do gateway de voz. Observe que é possível conectar um dispositivo da lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Nome do gateway de voz 1  <br/> |Usado para gerar o FQDN do computador com domínio do AD. Necessário se o TLS for usado entre o componente de mediação e o gateway de voz. Se você não planeja usar FQDN — por exemplo, o TLS não é necessário ou o gateway de voz não suporta conexão usando FQDN (apenas IP) — especifique.  <br/> ||
|Nome do gateway de voz 2 (Copie essa linha se tiver mais de dois gateways)  <br/> |Usado para gerar o FQDN do computador com domínio do AD. Necessário se o TLS for usado entre o componente de mediação e o gateway de voz. Se você não planeja usar FQDN — por exemplo, o TLS não é necessário ou o gateway de voz não suporta conexão usando FQDN (apenas IP) — especifique.  <br/> ||
|Endereço IP do gateway de voz 1  <br/> |Endereço IP do gateway de voz.  <br/> ||
|Endereço IP do gateway de voz 2 (Copie essa linha se tiver mais de dois gateways)  <br/> |Endereço IP do gateway de voz.  <br/> ||
|N º de porta do gateway de voz 1 (Copie essa linha se tiver mais de dois gateways)  <br/> |Porta na qual o tronco SIP do gateway de voz escutará, por exemplo, 5060.  <br/> ||
|Porta do gateway de voz 2 #  <br/> |Porta na qual o tronco SIP do gateway de voz escutará, por exemplo, 5060.  <br/> ||
|Protocolo para tráfego SIP do gateway de voz 1  <br/> |TCP ou TLS.  <br/> ||
|Protocolo para tráfego SIP do gateway de voz 2 (Copie essa linha se tiver mais de dois gateways)  <br/> |TCP ou TLS.  <br/> ||
|Intervalo de porta de mídia externa para o tráfego de e para o componente de borda  <br/> |Intervalo de portas TCP/UDP para tráfego de mídia de e para a interface externa da borda. Deve sempre começar a partir de 50 000. Consulte "portas e protocolos" para obter mais informações.  <br/> |50000-59 999  <br/> |
|Intervalo de porta de mídia para se comunicar com/do componente de mediação por meio do firewall interno  <br/> |Intervalo de portas UDP que o componente de mediação usará para se comunicar com clientes e gateways (recomendação de 4 portas por chamada).  <br/> ||
|Intervalo de porta de mídia para se comunicar com/do cliente do Skype for Business por meio do firewall interno  <br/> |Para fins de planejamento, não pode ser alterado. As portas precisam ser abertas no firewall interno para se comunicar entre os clientes do Skype for Business dentro da rede interna e com o componente de mediação.  <br/> |50 000-50 019  <br/> |
|Senha do certificado público  <br/> |Deve ser fornecido no script.  <br/> ||
|Senha de administrador do modo de segurança  <br/> Apenas a versão 1.4.2  <br/> |Senha do administrador do modo de segurança para o domínio CC interno.  <br/> ||
|Senha do administrador de domínio do Cloud Connector  <br/> Apenas a versão 1.4.2  <br/> |Senha para administrador de domínio do Cloud Connector (diferente do domínio de produção). O nome de usuário é administrador. Não é possível alterar o nome de usuário.  <br/> ||
|Senha de administrador das máquinas virtuais  <br/> Apenas a versão 1.4.2  <br/> |Usado para configurar a rede de gerenciamento durante a implantação.  <br/> O nome de usuário é administrador. Não é possível alterar o nome de usuário.  <br/> ||
|CABackupFile  <br/> Versão 2,0 e posterior  <br/> |Usado para salvar o serviço de autoridade de certificação do servidor do Active Directory em um arquivo ao implantar vários dispositivos em um site do Cloud Connector. Certifique-se de usar a mesma senha para todos os dispositivos em um site do Cloud Connector para importar o arquivo de backup da CA para o novo dispositivo adicionado com êxito.  <br/> ||
|CCEService  <br/> Versão 2,0 e posterior  <br/> |Usada para o serviço de gerenciamento do Cloud Connector; precisa acessar o diretório do site do Cloud Connector. Certifique-se de usar a mesma senha para todos os dispositivos em um site do Cloud Connector.  <br/> ||
|Administrador de locatários do Microsoft 365 ou do Office 365  <br/> | A conta é usada pelo Cloud Connector para atualizar e gerenciar as configurações de locatário do Cloud Connector: <br/>  Versão 2,0 e posterior: credenciais para uma conta dedicada do Microsoft 365 ou do Office 365 com direitos de administrador do Skype for Business. <br/>  Versões anteriores a 2,0: credenciais para uma conta dedicada do Microsoft 365 ou do Office 365 com direitos de administrador de locatário global. <br/> ||
|Habilitar o suporte de referência  <br/> |Isso definirá se o suporte de SIP de referência está habilitado ou desabilitado na configuração de tronco para o IP/PBX. O valor padrão é True. Se o seu gateway IP/PBX suportar o suporte de referência, deixe-o como verdadeiro. Caso contrário, esse valor precisa ser alterado para false. Se você não tiver certeza se o seu gateway oferece suporte à referência, confira [gateways e IP-PBXs qualificados](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versão 2,0 e posterior  <br/> |Com o valor padrão "true", se as chamadas de saída não forem atendidas pelo gateway dentro de 10 segundos, elas serão roteadas para o próximo gateway disponível; Se não houver troncos adicionais, a chamada será cancelada automaticamente.  <br/> No entanto, em uma organização com redes e respostas de gateway lentas, ou quando o processo de estabelecimento de chamadas demora mais de 10 segundos, isso pode resultar em chamadas descartadas desnecessariamente.  <br/> Ao fazer chamadas para alguns países, por exemplo, o Emirados ou Afeganistão, o processo de estabelecimento de chamada pode levar mais de 10 segundos. Você precisará alterar o valor para false se encontrar problemas semelhantes. Não se esqueça de alterar a configuração correspondente no SBC ou gateway conectado.  <br/> O valor pode ser true ou false. O valor padrão é True.  <br/> ||
|ForwardCallHistory  <br/> Versão 2,0 e posterior  <br/> | Esse parâmetro é usado para ativar cabeçalhos SIP que são usados para relatar o chamador inicial em cenários simultâneos de toque, encaminhamento de chamadas e transferência de chamadas. A definição do parâmetro como true ativará dois cabeçalhos SIP: <br/>  History-info <br/>  Referido por <br/>  O cabeçalho History-info é usado para redirecionar solicitações SIP e "fornecer (s) um mecanismo padrão para capturar as informações do histórico de solicitações para habilitar uma ampla variedade de serviços para redes e usuários finais" ([RFC 4244-seção 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Para as interfaces de tronco do Cloud Connector, isso é usado nos cenários toque simultâneo e encaminhamento de chamadas.  <br/>  O valor pode ser true ou false. O valor padrão é False. <br/> ||
|Encaminhar PAI  <br/> Versão 2,0 e posterior  <br/> |PAI é uma extensão privada para SIP que permite que servidores SIP declarem a identidade de usuários autenticados. Para o provedor de tronco SIP, PAI pode ser usado para fins de cobrança no caso de os cabeçalhos History-info e referido-by não estiverem presentes. Quando o encaminhamento P-Asserted-Identity é habilitado na configuração, o servidor de mediação encaminhará cabeçalhos PAI com os &amp; URIS SIP Tel do Cloud Connector para o tronco SIP. O servidor de mediação encaminhará cabeçalhos PAI com &amp; os números E. 164 do Tel URI recebidos somente no tronco SIP para o Cloud Connector. O servidor de mediação também encaminhará todos os cabeçalhos de privacidade recebidos em ambas as direções. Se a solicitação SIP enviada pelo servidor de mediação incluir um cabeçalho de privacidade da forma-"Privacy: ID" em conjunto com o cabeçalho PAI, a identidade declarada deverá ser mantida fora do domínio de confiança de rede.  <br/> O valor pode ser true ou false. O valor padrão é False.  <br/> ||

### <a name="certificate-requirements"></a>Requisitos de Certificação
<a name="BKMK_Certs"> </a>

Cada componente de borda requer um certificado de uma autoridade de certificação pública. Os certificados devem ter uma chave privada exportável para copiar entre os componentes de borda. Para atender aos requisitos de certificado, você precisará decidir entre as seguintes opções e fornecer o nome da entidade (SN) e o nome alternativo da entidade (SAN) para o certificado.

 **Se você tiver um único domínio SIP:**

- **Opção 1.** O nome da entidade deve conter o nome do pool que você atribuiu aos componentes de borda. Observe que o nome da entidade não pode ser sip.sipdomain.com porque esse nome está reservado para o componente de borda do Skype for Business online. A SAN deve conter sip.sipdomain.com e o nome do pool de borda de acesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opção 2.** Se quiser usar um único certificado curinga em todos os servidores do pool de Borda implantados, você poderá usar uma entrada de SAN curinga de \* . sipdomain.com em vez do nome do pool de borda no certificado. O nome da entidade pode ser o nome do pool de borda de acesso de qualquer um dos pools de Borda implantados:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para SIP. \< sipdomain \> . com porque esse nome pertence à implantação do Microsoft 365 ou do Office 365.

> [!NOTE]
> Se você quiser usar um único certificado para todos os pools de Borda implantados em sua organização e não puder usar um certificado curinga, conforme definido na opção 2, será necessário incluir o FQDN de todos os pools de Borda implantados no nome da SAN no certificado.

 **Se você tiver vários domínios SIP:**

Você precisará adicionar sip.sipdomain.com para cada domínio SIP e o nome dos pools de borda de acesso por domínio (pode ser um pool físico, mas com nomes diferentes). Veja a seguir um exemplo de entradas de SN e SAN em um cenário de vários domínios SIP:

- **Opção 1.** O nome da entidade deve conter o nome do pool que você atribuiu aos componentes de borda. Observe que o nome da entidade não pode ser sip.sipdomain.com porque esse nome está reservado para o componente de borda do Skype for Business online. A SAN deve conter sip.sipdomain.com e o nome do pool de borda de acesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opção 2.</strong> Se quiser usar um único certificado curinga em todos os servidores do pool de Borda implantados, você poderá usar uma entrada de SAN curinga de \* . sipdomain.com em vez do nome do pool de borda no certificado. O nome da entidade pode ser o nome do pool de borda de acesso de qualquer um dos pools de Borda implantados:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para SIP. \< sipdomain \> . com porque esse nome pertence à implantação do Microsoft 365 ou do Office 365.

Para fins de implantação, você pode usar a seguinte tabela:

|**Opção**|**Descrição**|**Anotações**|
|:-----|:-----|:-----|
|Qual opção você usará para sua implantação?  <br/> |Opção 1 ou 2  <br/> ||
|SN  <br/> |Fornecer o SN para seu certificado  <br/> ||
|SAN  <br/> |Fornece a SAN para seu certificado  <br/> ||

Se você estiver usando o TLS entre o gateway e o servidor de mediação, será necessário obter o certificado raiz ou a cadeia de certificados completo para o certificado atribuído ao gateway.

## <a name="dial-plan-considerations"></a>Considerações do plano de discagem
<a name="BKMK_DailPlan"> </a>

O Cloud Connector requer o uso de um plano de discagem online. Para obter mais informações sobre como configurar um plano de discagem online, consulte [o que são planos de discagem?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerações sobre alta disponibilidade
<a name="BKMK_HA"> </a>

Ao implantar o Cloud Connector Edition para alta disponibilidade, você implanta pelo menos dois dispositivos que atuam como um backup para um do outro. Cada dispositivo consiste em quatro componentes: Edge, mediação, repositório de gerenciamento central (CMS) e controlador de domínio.

Em geral, se um componente em um dispositivo for desativado, o Cloud Connector Edition poderá continuar a lidar com as chamadas, mas você deve considerar o seguinte:

- **Considerações sobre componentes de mediação, CMS e controlador de domínio**

    Suponha que o componente CMS ou controlador de domínio em um dispositivo inativo. O dispositivo ainda pode lidar com chamadas de entrada e de saída, mas se você reiniciar um componente de mediação quando o controlador de domínio ou o componente CMS não estiver acessível, a mediação não funcionará. O mesmo se aplica ao reinício do componente CMS quando o controlador de domínio está inoperante.

    **Recomendação:** Antes de reiniciar componentes, verifique a disponibilidade dos outros componentes no dispositivo.

- **Considerações sobre componentes de borda**

    Se o componente de borda em um dispositivo não estiver disponível, o comportamento das chamadas de entrada e de saída será diferente da seguinte maneira:

  - **Chamada de saída**– uma chamada do seu usuário na Internet para uma rede PSTN.

    O mecanismo de distribuição de chamadas na nuvem identificará que um componente de borda está inoperante e encaminhará todas as chamadas para outro dispositivo, para que a chamada de saída seja bem-sucedida.

  - **Chamada de entrada**– uma chamada da rede PSTN para um usuário que esteja em uma rede local ou na Internet.

     Se o componente de borda do dispositivo que recebeu a chamada não estiver funcionando, as chamadas de entrada para esse dispositivo não serão bem-sucedidas, pois o componente de mediação não poderá redirecionar a chamada para o componente de borda no outro dispositivo.

    **Recomendação:** Ter um sistema de monitoramento em vigor. Após identificar um mau funcionamento do componente de borda, desative todos os componentes no dispositivo em que o componente de borda não está disponível.

## <a name="cloud-connector-media-flow"></a>Fluxo de mídia do Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Os seguintes diagramas descrevem o fluxo de uma chamada de entrada e de saída por meio do Cloud Connector Edition. Esta é uma informação útil para entender como a conectividade é estabelecida.

No primeiro diagrama, um usuário interno coloca uma chamada de saída da seguinte maneira:

1. Dave, um usuário hospedado online, mas que agora está na rede interna, faz uma chamada para um usuário PSTN externo.

2. Rotas de tráfego SIP para o Skype for Business online.

3. O Skype for Business online executa uma pesquisa de número inverso do número. A pesquisa de número reverso falha porque esse número não pertence a qualquer pessoa na organização do Skype for Business.

4. A chamada é roteada para o componente de borda (SIP e fluxo de mídia via borda online primeiro; A mídia vai para o componente de mediação por meio do firewall interno).

5. Se a rota existir, o componente de borda retransmitirá o tráfego para o componente de mediação na rede de perímetro.

6. O componente de mediação envia o tráfego para o gateway PSTN.

![Fluxo de mídia de saída para o Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

No próximo diagrama, um usuário interno recebe uma chamada de entrada da seguinte maneira:

1. O gateway PSTN recebe uma chamada para o usuário Dave, que está hospedado online, mas agora está na rede interna.

2. O tráfego SIP é roteado para o componente de mediação.

3. O componente de mediação envia o tráfego SIP ao componente de borda e, em seguida, vai para o Skype for Business online.

4. O Skype for Business online executa uma pesquisa de número inverso do número e descobre que se trata do usuário Dave.

5. A sinalização SIP vai para todos os pontos de presença de Dave.

6. O tráfego de mídia será estabelecido entre o gateway e o componente de mediação e entre o componente de mediação e o ponto final.

![Fluxo de mídia de entrada para o Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoramento e solução de problemas
<a name="BKMK_Monitor"> </a>

O mecanismo de monitoramento e solução de problemas é instalado automaticamente com cada dispositivo do Cloud Connector. O mecanismo detecta os seguintes eventos:

- Uma ou mais máquinas virtuais de um dispositivo do Cloud Connector não estão conectadas a um comutador virtual interno ou Internet.

- Uma ou mais máquinas virtuais de um dispositivo do Cloud Connector estão no status salvo ou parado.

- Serviços que não estão em execução.

  Se um dos eventos a seguir for detectado, todo o dispositivo do Cloud Connector será esvaziado e marcado como offline para impedir a tentativa de estabelecer chamadas para um dispositivo defeituoso. Os recursos de recuperação automática do Cloud Connector irão restaurar serviços posteriormente e marcar o dispositivo como online. Se a recuperação automática falhar por algum motivo, confira [solucionar problemas de implantação do Cloud Connector](troubleshoot-your-cloud-connector-deployment.md).

  - Na máquina virtual do repositório de gerenciamento central:

     - Agente do Skype for Business Master Replicator

     - Agente replicador de réplica do Skype for Business

  - Na máquina virtual do servidor de mediação:

     - Agente replicador de réplica do Skype for Business

     - Mediação do Skype for Business Server

  - Na máquina virtual do servidor de borda

     - Agente replicador de réplica do Skype for Business

     -  Borda de acesso do Skype for Business Server

     - Borda de áudio/vídeo do Skype for Business Server

     - Autenticação de áudio/vídeo do Skype for Business Server

     - Borda de Webconferência do Skype for Business Server

- Regra de entrada do firewall do Windows para "CS RTCSRV" no Edge, "CS RTCMEDSRV" no servidor de mediação está desabilitado.

O Cloud Connector 2,1 e posterior suporta o monitoramento do Cloud Connector usando o Operations Management Suite (OMS). Para obter mais informações, consulte [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_MoreInfo"> </a>

Para obter mais informações, confira:

- [Soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configurar e gerenciar o Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Plano para bypass de mídia no Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Implantar bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


