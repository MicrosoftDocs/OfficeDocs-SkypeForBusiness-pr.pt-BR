---
title: Plano do Skype for Business Edição Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Encontre informações sobre o Skype for Business Cloud Connector Edition, um conjunto de máquinas virtuais (VMs) compactadas que implementam conectividade PSTN local com o Sistema de Telefonia do Office 365 (Cloud PBX).
ms.openlocfilehash: 3b95c1cca24b6faac8a6cf2807b6af324fdc57bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002271"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Plano do Skype for Business Edição Cloud Connector

Encontre informações sobre o Skype for Business Cloud Connector Edition, um conjunto de máquinas virtuais (VMs) compactadas que implementam conectividade PSTN local com o Sistema de Telefonia do Office 365 (Cloud PBX).

O Cloud Connector Edition pode ser a solução certa para a sua organização se você ainda não tiver uma implantação existente do Lync Server ou do Skype for Business Server. Se você ainda estiver investigando qual sistema telefônico da solução do Office 365 é ideal para a sua empresa, consulte [soluções de telefonia da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Este documento descreve os requisitos da edição do Cloud Connector e as topologias compatíveis e ajuda você a planejar sua implantação do Cloud Connector Edition. Não deixe de ler este tópico antes de configurar o ambiente do conector de nuvem. Quando estiver pronto para implantar e configurar a edição do conector de nuvem, consulte [configurar e gerenciar o Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

O Cloud Connector Edition 2,1 agora está disponível. Se você ainda não tiver atualizado para a versão 2.1, veja [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Você pode encontrar o arquivo de instalação [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)em.

> [!NOTE]
> A Microsoft oferece suporte à versão anterior da edição do Cloud Connector para 60 dias após o lançamento de uma nova versão. A Microsoft dará suporte para a versão 2.0.1 por 60 dias após o lançamento da versão 2.1 para que você tenha tempo para fazer a atualização. Não há mais suporte para as versões anteriores à 2.0.1.

O Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de máquinas virtuais compactadas (VMs) que implementam a conectividade PSTN local com o sistema telefônico no Office 365. Ao implantar uma topologia mínima do Skype for Business Server em um ambiente virtualizado, os usuários em sua organização que são hospedados na nuvem podem receber serviços de PBX da nuvem da Microsoft, mas a conectividade PSTN é fornecida por meio da voz local existente admin.

![Diagrama de topologia mostrando o Cloud PBX gateway conectando o Cloud PBX a uma implantação local do Skype for Business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Já que o Cloud Connector permite integrar os serviços do Sistema de Telefonia do Office 365 com o seu ambiente de telefonia existente, por exemplo, PBX, dispositivos analógicos e Call Centers, você pode implementar uma migração em fases da sua solução de telefonia existente para o Sistema de Telefonia do Office 365.

Por exemplo, suponha que sua empresa tenha um Call Center sofisticado com uma funcionalidade específica que o Sistema de Telefonia do Office 365 não oferece. Você pode optar por deixar os usuários do Call Center com a solução existente, mas migrar outros usuários para o Sistema de Telefonia do Office 365.

O Cloud Connector fornecerá o roteamento entre os usuários hospedados no local e online, e você pode optar por usar o seu próprio provedor de PSTN com o Sistema de Telefonia do Office 365.

Considere o seguinte ao planejar sua implantação do Cloud Connector Edition:

- Para usar o conector de nuvem para tirar proveito das soluções de voz em nuvem, você precisa se inscrever para um locatário do Office 365 que inclua o sistema telefônico no Office 365. Se você ainda não tiver um locatário do Office 365, poderá aprender a se inscrever aqui: [Office 365 para empresas](https://products.office.com/en-us/business/office). Observe que você precisará se inscrever para um plano que inclua o Skype for Business online.

- Para registrar os aparelhos de conector de nuvem com o serviço do Skype for Business Online e para executar vários cmdlets, o Cloud Connector 2,0 e posterior exige uma conta dedicada do Office 365 com os direitos de administrador de locatários do Skype for Business. As versões do Cloud Connector anteriores à 2.0 exigem uma conta dedicada do Office 365 com direitos de administrador global de locatários.

- O Cloud Connector não requer uma implantação completa do Skype for Business Server.

    Atualmente, o conector de nuvem não pode coexistir com servidores do Lync ou do Skype for Business no local. Se você quiser mover os usuários existentes do Lync ou Skype for Business para o Office 365 e continuar a fornecer a telefonia local aos seus usuários, considere o sistema telefônico no Office 365 com conectividade local usando uma implantação existente do Skype for Business Server. Para obter mais informações, consulte [planejar o sistema telefônico na solução do office 365 (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md) e [planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se você tiver uma implantação anterior do Skype for Business ou do Lync Server e estendido o esquema, não será necessário limpar o esquema para a implantação do conector de nuvem, desde que todos os componentes do Skype for Business ou do Lync Server sejam removidos do seu ambiente.

- Os usuários estão hospedados on-line.

- Se sua organização tiver configurado a DirSync (Sincronização de diretórios), todas as contas de usuários que estão planejadas para voz híbrida devem ser criadas primeiro na sua implantação local e depois sincronizadas com a nuvem.

- É possível manter sua operadora de PSTN atual, se necessário.

- Se você quiser fornecer conferência discada para os usuários hospedados no Cloud Connector, você pode comprar a licença de conferência PSTN ou a oferta de conferência de áudio do pré-pago da Microsoft.

- A licença de audioconferência (ou oferta pré-pago) também é necessária para escalonamentos de chamadas. Se um usuário do Skype for Business receber uma chamada de um usuário PSTN externo e quiser adicionar mais um participante a essa chamada (escalonar a chamada para uma conferência), o escalonamento será realizado por meio do serviço de conferência de áudio da Microsoft.

- Agora, o Cloud Connector 2.0 e versões posteriores têm suporte para bypass de mídia. O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da rede telefônica pública comutada (PSTN), um gateway ou um controlador de borda de sessão (SBC), e elimine o componente da edição do conector de nuvem do caminho de mídia. Para obter mais informações, consulte [plano de bypass de mídia na edição do conector de nuvem](plan-for-media-bypass-in-cloud-connector-edition.md).

- O Cloud Connector 2.1 e versões posteriores dão suporte ao monitoramento do Cloud Connector usando o OMS (Operations Management Suite). Para obter mais informações, veja [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

- O Cloud Connector está disponível em todos os países onde o Office 365 Enterprise E5 está disponível.

Este tópico inclui as seguintes seções:

- [Componentes da Edição Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologias da Edição do Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisitos para a implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informações que você precisa coletar antes da implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerações sobre plano de discagem](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerações sobre alta disponibilidade](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Fluxo de mídia do Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoramento e solução de problemas](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Para obter mais informações](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componentes da Edição Cloud Connector
<a name="BKMK_Components"> </a>

Com o Cloud Connector Edition, você implanta um conjunto de VMs empacotadas que contêm uma topologia mínima do Skype for Business Server, que consiste em um componente Edge, componente de mediação e uma função CMS (repositório central de gerenciamento). Você também instalará um controlador de domínio, que é necessário para o funcionamento interno do conector de nuvem. Esses serviços são configurados para híbrido com o seu locatário do Office 365, que inclui os serviços do Skype for Business online.

![Componentes da Edição Cloud Connector](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Os componentes do conector de nuvem oferecem a seguinte funcionalidade:

- **Componente Edge** – a comunicação entre a topologia local e os serviços online passa pelo componente Edge, que inclui os seguintes componentes:

  - **Edge do Access** : fornece roteamento SIP entre a implantação local e o Skype for Business online.

  - **Media Relay** : fornece o roteamento de mídia entre o componente de mediação e outros pontos de extremidade de mídia.

  - **Autenticação de retransmissão de mídia/MRAS** -gera tokens para acesso ao Media Relay.

- **Roteamento de saída** -fornece balanceamento de carga do tráfego de voz entre gateways ou SBCS conectados a um aparelho de conector de nuvem. As chamadas serão divididas igualmente entre os gateways ou os SBCs conectados ao dispositivo do Cloud Connector.

    Fornece o roteamento para gateways com base em políticas. Só há suporte para políticas globais que se baseiam em números PSTN de destino (saída).

- **Função do CMS (repositório central de gerenciamento)** -inclui o repositório de configuração para os componentes de topologia, incluindo a transferência de arquivos CMS.

- **Réplica do repositório de gerenciamento central (CMS)** -sincroniza as informações de configuração do banco de dados do CMS global no servidor de funções CMS.

- **Controlador de domínio** -serviços de domínio do Active Directory do conector de nuvem para armazenar todas as configurações globais e grupos necessários para implantar componentes do conector de nuvem. Uma floresta será criada para cada aparelho do Cloud Connector. O controlador de domínio não deve ter nenhuma conexão com o Active Directory de produção. Os serviços do Active Directory incluem:

  - Serviços de Domínio Active Directory

  - Serviços de Certificado do Active Directory para emitir certificados internos

- **Componente de mediação** -implementa o protocolo SIP e o protocolo de mapeamento do gateway de mídia entre os gateways PSTN e PSTN do Skype for Business. Inclui uma réplica CMS que sincroniza a configuração do banco de dados CMS global.

## <a name="cloud-connector-edition-topologies"></a>Topologias da Edição do Cloud Connector
<a name="BKMK_Topologies"> </a>

Para os fins desta discussão, vamos nos referir a sites PSTN. Um site PSTN é uma combinação de aparelhos de conector de nuvem, implantada no mesmo local e com gateways PSTN comuns conectados a eles. Os sites PSTN permitem:

- Fornecer conectividade aos gateways mais próximos aos usuários.

- Permita a escalabilidade implantando vários dispositivos de conector de nuvem em um ou mais sites PSTN.

- Permita alta disponibilidade implantando vários dispositivos de conector de nuvem em um único site PSTN.

Neste tópico, são apresentados os sites PSTN. Para obter mais informações sobre o planejamento de seus sites PSTN, veja [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Você pode implantar as seguintes topologias de conector de nuvem:

- Um único dispositivo do Cloud Connector Edition por site PSTN. Essa topologia é recomendada apenas para fins de avaliação, pois não fornece alta disponibilidade.

- Vários appliances do Cloud Connector Edition por site PSTN para fornecer alta disponibilidade.

- Vários sites PSTN com vários appliances do Cloud Connector Edition para fornecer escalabilidade com alta disponibilidade. Você pode implantar até 200 sites.

Ao planejar sua topologia, considere o seguinte:

- Com o Cloud Connector 2,0 e posterior, um site PSTN pode ter até 16 aparelhos de conector de nuvem. As versões anteriores suportam até 4 dispositivos por site.

- Há dois tipos de configurações de hardware testada com o conector de nuvem:

  - A versão grande é capaz de processar grandes volumes de chamadas simultâneas e é compatível com todos os tipos de ambientes de produção.

  - A versão pequena deve ser executada em hardware lower-end e pode ser utilizada para avaliação ou para sites com baixos volumes de chamadas. Se você implantar uma versão pequena do Cloud Connector, precisará ficar atento aos requisitos do hardware de classe de produção (como fontes de alimentação duplas).

- Se você tiver a versão 2,0 ou posterior do Cloud Connector e implantar a configuração máxima de 16 dispositivos (com hardware maior), o seu site PSTN pode manipular até 8.000 chamadas simultâneas. Se você implantar a versão menor, o limite suportado será 800.

    Você também precisa dedicar alguns dispositivos para a alta disponibilidade. A recomendação mínima é que um dispositivo seja reservado para a alta disponibilidade.

  - Com a versão 2, se você implantar uma configuração de 15 + 1, o seu site PSTN pode manipular até 7.500 chamadas simultâneas.

  - Se você tiver uma versão anterior e implantar a configuração máxima de 3 + 1 (com hardware grande), seu local de PSTN poderá processar até 1.500 chamadas simultâneas. Se você implantar a versão pequena, o limite suportado será 150.

-  Se houver a necessidade de mais chamadas por site PSTN, é possível aumentar a escala ao implantar sites PSTN adicionais no mesmo local.

> [!NOTE]
> A menos que observado, os diagramas e exemplos a seguir pressupõem o uso da versão maior do conector de nuvem.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Um único dispositivo do Cloud Connector em um único site PSTN

O diagrama a seguir mostra um único aplicativo Cloud Connector Edition em um único site PSTN. Observe que o conector de nuvem consiste em quatro VMs instaladas em um computador host físico que está dentro de uma rede de perímetro para fins de segurança.

![Um conector de nuvem com um site PSTN](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Vários dispositivos do Cloud Connector em um único site PSTN

 Para fins de escalabilidade e alta disponibilidade, você pode optar por ter várias edições do conector de nuvem em um único site PSTN, conforme mostrado no diagrama a seguir. Considere o seguinte:

- As chamadas são distribuídas em ordem aleatória entre as instâncias do Cloud Connector em um pool.

- Para fins de planejamento de capacidade, você deve considerar a capacidade de lidar com a carga caso uma ou mais instâncias do Cloud Connector fiquem offline, com base nos seguintes cálculos:

  - **N+1 caixas.** Para a versão maior do Cloud Connector, N + 1 caixas dão suporte\*a 500 N chamadas simultâneas com 99,8% de disponibilidade.

    Para a versão menor do conector de nuvem, N + 1 caixas dão\*suporte a 50 N chamadas simultâneas com 99,8% de disponibilidade.

  - **N+2 caixas.** Para a versão maior do conector de nuvem, N + 2 caixas dão\*suporte a 500 N chamadas simultâneas com 99,9% de disponibilidade.

    Para a versão menor do conector de nuvem, N + 2 caixas dão\*suporte a 50 N chamadas simultâneas com 99,9% de disponibilidade.

![Dois conectores de nuvem dentro de 1 site PSTN](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Vários sites PSTN com uma ou mais instâncias de Cloud Connector por site

Também é possível ter vários locais de PSTN com uma ou mais instâncias de Cloud Connector Edition em cada site. Se o seu local de PSTN atingir o limite de chamadas simultâneas, será possível adicionar outro local de PSTN para lidar com a carga.

Vários sites PSTN também permitem que você forneça conectividade com gateways mais próximos aos seus usuários. Por exemplo, suponha que você tenha gateways PSTN em Seattle e Amsterdã. Você pode implantar dois sites PSTN, um em Seattle, um em Amsterdã — e atribuir usuários para usar o site PSTN mais próximo deles. Os usuários de Seattle serão roteados para o site PSTN de Seattle e para os gateways, enquanto os usuários em Amsterdã serão roteados para os gateways e o site PSTN do Amsterdã:

![Edição Cloud Connector em 2 Sites PSTN](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisitos para a implantação
<a name="BKMK_Requirements"> </a>

Antes de implantar o Cloud Connector Edition, verifique se você tem o seguinte para o seu ambiente:

- **Para o computador host-** As VMs do conector de nuvem devem ser implantadas em hardware dedicado executando o Windows Server 2012 R2 Datacenter Edition (inglês) com a função Hyper-V habilitada.

    Para a versão 2.0 e posteriores, a placa de rede do computador host vinculada ao comutador da rede corporativa do Skype for Business deve ter um endereço IP configurado na mesma sub-rede que as máquinas da rede corporativa do Cloud Connector. 

- Para as versões 2,1 e posteriores, o aplicativo host deve ter o .NET Framework 4.6.1 ou posterior instalado.

- **Para as máquinas virtuais-** Uma imagem ISO (inglês) do Windows Server 2012 R2 (. ISO). O ISO será convertido em VHDs para as máquinas virtuais que executarão o Skype for Business Cloud Connector Edition.

- O hardware necessário para dar suporte à instalação das 4 VMs para cada edição do conector de nuvem na sua implantação. São recomendadas as seguintes configurações:

  - processador dual de 64 bits, seis núcleos (12 núcleos reais), 2,50 gigahertz (GHz) ou superior

  - 64 gigabytes (GB) de RAM ECC 

  - Quatro discos SAS de 6Gbps de Cache 128M de 10K de RPM configurados em uma configuração RAID 5

  - Três adaptadores de rede de alto rendimento RJ45 de 1 Gbps

- Se optar por implantar a versão menor do Cloud Connector Edition compatível com até 50 chamadas simultâneas, você precisará do seguinte hardware:

  - Intel i7 4790 quad core com gráficos Intel 4600 (não é necessário ter gráficos de alta tecnologia)

  - 32 GB DDR3-1600 não ECC

  - 2: 1TB 7200RPM SATA III (6 Gbps) em RAID 0

  - 2: Ethernet de 1 Gbps (RJ45)

- Se um servidor proxy for necessário no computador host para se navegar na Internet, você deverá fazer as seguintes alterações de configuração:

  - Para ignorar o proxy, especifique as configurações de proxy WinHTTP definidas com o servidor proxy e uma lista de ignorados, incluindo o "192.168.213. \*"rede usada por seus serviços de gerenciamento de conector de nuvem e pela sub-rede do Skype for Business corpnet conforme definido em seu arquivo. ini do CloudConnector. Caso contrário, a conectividade de gerenciamento falhará e impedirá a implantação e a recuperação automática do Cloud Connector. Veja a seguir um exemplo de comando de configuração do WinHTTP: netsh WinHTTP Set proxy "10.10.10.175:8080" bypass-\*List = ". local; 1. \*; 172,20. \*; 192.168.218. \*"\<local\>".

  - Especifique as configurações de proxy por máquina, em vez de por usuário. Caso contrário, os downloads do conector de nuvem falharão. Você pode especificar as configurações de proxy por máquina com uma alteração no Registro ou com a configuração de Política de Grupo da seguinte forma:

  - **Registro:** HKEY_LOCAL_MACHINE configurações de \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Política de Grupo:** Modelos\>\>administrativos do computador\> Internet Explorer para Windows: fazer configurações de proxy por máquina (em vez de por usuário)

- PBX/Tronco qualificado ou SBC/Gateway qualificado (um mínimo de dois gateways é recomendado).

    O Cloud Connector dá suporte aos mesmos SBCs (Controladores de Borda da Sessão) que são certificados para o Skype for Business. Para obter mais informações, consulte [infraestrutura de telefonia do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Uma conta de administrador do servidor local com permissões para instalar e configurar o Hyper-V nos servidores host. A conta deve ter permissões de administrador no servidor local onde o Hyper-V está instalado e configurado.

- Durante a implantação, você será solicitado a criar uma conta de administrador de domínio com as permissões para criar e publicar a topologia no domínio do Cloud Connector. 

- Os registros DNS externos, que são definidos no arquivo CloudConnector.ini incluído no pacote de instalação:

  - Registro DNS externo para serviço de borda de acesso do componente de extremidade; por exemplo, AP.\<nome\>do domínio. Você precisa de um registro por local de PSTN. Esse registro deve conter endereços IP de todas as Bordas desse local.

- Um locatário do Office 365 com todos os registros DNS e SRV necessários criados.

    > [!IMPORTANT]
    > Quando você integra seu locatário com o Cloud Connector Edition, não há suporte para o uso do sufixo de domínio padrão,. onmicrosoft.com, como um domínio SIP para a sua organização. > não é possível usar o SIP. \<Nome\> do domínio como o nome de sua interface proxy de acesso à borda do conector de nuvem porque esse registro DNS é usado pelo Office 365.

- Um certificado para a Borda externa obtido de uma Autoridade de Certificação (CA) pública

- As regras de Firewall para permitir o tráfego através da portas necessárias foram concluídas.

- Uma conexão com a Internet para o computador host e as VMs. O Cloud Connector baixa alguns softwares da Internet; Portanto, você deve fornecer informações do servidor DNS e do gateway para que a máquina host do conector de nuvem e VMs possam se conectar à Internet e baixar o software necessário.

- Um módulo remoto do PowerShell do locatário instalado no computador host.

- As credenciais de administrador do Office 365 Skype for Business para a execução do PowerShell remoto.

    > [!IMPORTANT]
    > A conta do administrador NÃO DEVE ter a autenticação multifator habilitada.

> [!NOTE]
> A implantação do conector de nuvem só tem suporte na plataforma virtualizada do Microsoft Hyper-V. Outras plataformas, como VMware e Amazon Web Services, não têm suporte.

> [!NOTE]
> A orientação de hardware mínima para executar o conector de nuvem baseia-se na capacidade básica de hardware (núcleos, MHz, gigabytes e assim por diante) com algum buffer para acomodar deficiências de desempenho intangível enterradas na arquitetura de qualquer computador. A Microsoft executou o pior caso de teste de carga em um hardware comercialmente disponível e que atendia a orientação mínima. A qualidade da mídia e o desempenho do sistema são verificados. Os parceiros oficiais da ferramenta de conector de nuvem da Microsoft têm implementações específicas de hardware do conector de nuvem em que o desempenho foi testado de modo independente e eles representam a adequação do seu hardware para atender aos requisitos de carga e qualidade.

> [!NOTE]
> Os dispositivos produzidos pela AudioCodes e pela Sonus têm código modificado e são executados nos servidores Windows Server Standard Edition. Há suporte para esses dispositivos.

## <a name="information-you-need-to-gather-before-deployment"></a>Informações que você precisa coletar antes da implantação
<a name="BKMK_PlanDeployment"> </a>

Antes de iniciar sua implantação, será necessário determinar o tamanho de sua implantação, os domínios SIP que estão sendo atendidos e as informações de configuração para cada site PSTN que você planeja implantar. Para começar, você deve:

- Identifique todos os domínios SIP que serão servidos por essa implantação com base nos URIs SIP em uso na sua empresa.

- Determinar o número de sites PSTN que você precisa implantar.

- Verifique se você tem o hardware necessário para dar suporte às quatro VMs que você está instalando para cada edição do Cloud Connector.

Para cada site PSTN que você planeja implantar, você precisa:

- Crie nomes para todos os componentes em cada dispositivo de conector de nuvem (consulte [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definir intervalos de porta (consulte [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)). 

- Criar registros DNS externos para o componente de Borda (veja [Requisitos para implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinar os requisitos de certificado para o componente de Borda (veja [Requisitos de certificado](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Portas e protocolos
<a name="BKMB_Ports"> </a>

Ao definir os intervalos de porta de mídia, esteja ciente do seguinte:

- Os clientes sempre usam o intervalo de porta 50000 a 50019 para tráfego de mídia — esse intervalo é predefinido no Skype for Business Online e não pode ser alterado.

- O componente de Mediação usa, por padrão, o intervalo de porta 49.152 a 57.500 para o tráfego de mídia. No entanto, a conexão é estabelecida por meio do firewall interno e, por motivos de segurança, você pode limitar esse intervalo de porta na sua topologia. Serão necessárias até 4 portas por chamada. Se quiser limitar o número de portas entre o componente de Mediação e o gateway PSTN, também será preciso configurar o intervalo da porta correspondente no gateway.

- Você deve implantar o conector de nuvem em uma rede de perímetro. Isso significa que você terá dois firewalls:

  - O primeiro firewall será externo entre a Internet e sua rede de perímetro.

  - O segundo firewall é interno entre a rede de perímetro e a rede interna.

    Os clientes podem estar na Internet ou na rede interna: 

  - Clientes na Internet serão conectados ao seu PSTN através do firewall externo e do componente de Borda.

  - Os clientes na rede interna serão conectados por meio do firewall interno ao componente de mediação na rede de perímetro, o que conectará o tráfego ao gateway SBC ou PSTN.

    Isso significa que será preciso abrir as portas em ambos os firewalls. 

As tabelas a seguir descrevem as portas e os intervalos de portas para o firewalls internos e externos.

Essa tabela mostra as portas e os intervalos de portas para a habilitação da comunicação entre os clientes na rede interna e o componente de Mediação:

**Firewall interno**



|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Componente de remediação do conector de nuvem  <br/> |SBC/Gateway de PSTN:  <br/> |Qualquer um  <br/> |TCP 5060\*\*  <br/> |
|SBC/Gateway de PSTN:  <br/> |Componente de remediação do conector de nuvem  <br/> |Qualquer um  <br/> |TCP 5068/TLS 5067  <br/> |
|Componente de remediação do conector de nuvem  <br/> |SBC/Gateway de PSTN:  <br/> |UDP 49 152-57 500  <br/> |Qualquer\*\*\*  <br/> |
|SBC/Gateway de PSTN:  <br/> |Componente de remediação do conector de nuvem  <br/> |Qualquer\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Componente de remediação do conector de nuvem  <br/> |Clientes internos  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50.000-50.019  <br/> (Opcional)  <br/> |
|Componente de remediação do conector de nuvem  <br/> |Clientes internos  <br/> |UDP 49 152-57 500\*  <br/> |Clientes internos  <br/> |
|Clientes internos  <br/> |Componente de remediação do conector de nuvem  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clientes internos  <br/> |Componente de remediação do conector de nuvem  <br/> |Clientes internos  <br/> |UDP 49 152-57 500\*  <br/> |

\*Esse é o intervalo de portas padrão no componente de mediação. Para obter o melhor fluxo de chamadas, quatro portas por chamada são necessárias.

\*\*Essa porta deve ser configurada no gateway SBC/PSTN; 5060 é um exemplo. Você pode configurar outras portas no SBC/gateway de PSTN.

\*\*\*Observe que você também pode limitar o intervalo de porta em seu SBC/gateway, se permitido pelo fabricante de SBC/gateway.

Para fins de segurança, você pode limitar o intervalo de porta do componente de mediação usando o cmdlet [set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Por exemplo, o comando a seguir limita o número de portas que o componente de mediação usará para o tráfego de mídia para 50 000-51 000 para áudio (in and out). O componente de Mediação poderá administrar 250 chamadas simultâneas com essa configuração. Observe que você também pode querer limitar esse intervalo no SBC/gateway de PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Para recuperar o nome do componente de mediação e ver portas padrão, você pode usar o cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) da seguinte maneira:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

A tabela a seguir mostra portas e intervalos de portas para permitir a comunicação entre o componente de borda do conector de nuvem para o firewall externo. A tabela mostra a recomendação mínima.

Nesse caso, todo o tráfego de mídia para a Internet fluirá pela borda online da seguinte maneira: ponto final do usuário\>– borda online-\>-borda do conector da nuvem:

**Firewall externo - configuração mínima**



|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP 80  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |UDP 53  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP 53  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

A tabela a seguir mostra portas e intervalos de porta para habilitar a comunicação entre o componente de borda do conector de nuvem para o firewall externo. Esta tabela mostra a solução recomendada.

Nesse caso, todo o tráfego de mídia para o ponto de extremidade na Internet pode fluir diretamente para o componente de borda do conector da nuvem. O caminho de mídia será o ponto final do\> usuário-borda do conector da nuvem.

> [!NOTE]
> Essa solução não funcionará se o ponto de extremidade do usuário estiver usando um NAT simétrico.

**Firewall externo - configuração recomendada**


|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|
|:-----|:-----|:-----|:-----|
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP 80  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |UDP 53  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um   <br/> |Qualquer um  <br/> |TCP 53  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |TCP 50.000-59.999  <br/> |Qualquer um  <br/> |
|Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |UDP 3478; UDP 50,000-59,999  <br/> |Qualquer um   <br/> |
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |TCP 443; TCP 50,000-59,999  <br/> |
|Qualquer um  <br/> |Interface externa de borda do conector de nuvem  <br/> |Qualquer um  <br/> |Requisitos de conectividade com a Internet do host  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisitos de conectividade com a Internet do host
<a name="BKMB_Ports"> </a>

O computador host deve ser capaz de alcançar recursos externos para instalar, atualizar e gerenciar o conector de nuvem com êxito. A tabela a seguir mostra os destinos e portas necessários entre o computador host e os recursos externos.

|Direção  <br/> |IP de origem  <br/> |IP de destino  <br/> |Porta de origem  <br/> |Porta de Destino  <br/> |Protocolo  <br/> |Objetivo  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Saída  <br/> |IPs do host do conector de nuvem  <br/> |qualquer um  <br/> |qualquer um  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Saída  <br/> |IPs do host do conector de nuvem  <br/> |qualquer um  <br/> |qualquer um  <br/> |80, 443  <br/> |TCP  <br/> |Lista de certificados revogados (CRL)  <br/> |
|Saída  <br/> |IPs de host do conector de nuvem  <br/> |qualquer um  <br/> |qualquer um  <br/> |80, 443  <br/> |TCP  <br/> |Atualização do conector de nuvem  <br/> PowerShell do Administrador  <br/> PowerShell do Administrador  <br/> Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |

Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:

- [URLs da lista de certificados revogados](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) nas [URLs e nos intervalos de endereços IP do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [como configurar um firewall para atualizações de software](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- PowerShell de administração do Skype for Business \*online:. online.Lync.com

    Se precisar de uma exclusão de proxy para esse destino, você precisará adicioná-lo à lista de bypass do WinHTTP.

- Atualização do conector de nuvem: centro [https://go.microsoft.com](https://go.microsoft.com)de [Download](https://aka.ms/CloudConnectorInstaller), e[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Resolução de nome DNS para o componente de Borda
<a name="BKMB_Ports"> </a>

O componente Edge precisa resolver os nomes externos dos serviços do Office 365 e os nomes internos de outros componentes do conector de nuvem.

Cada componente de Borda é um computador multihomed com interfaces voltadas para o exterior e o interior. O Cloud Connector implanta servidores DNS no componente de controlador de domínio dentro da rede de perímetro. Você pode apontar o servidor de borda para o servidor DNS dentro do perímetro para todas as resoluções de nomes, mas é necessário habilitar o servidor DNS do conector de nuvem para resolver nomes externos definindo uma zona DNS contendo um ou mais registros DNS A para consultas externas que fazem referência a nome pesquisas em outros servidores DNS públicos.

No arquivo .ini, se você definir o nome FQDN para gateways do mesmo espaço de domínio que seu domínio SIP, a zona autoritativa para esse domínio SIP será criada no servidor DNS dentro do perímetro. Se o servidor de borda for apontado para este servidor DNS para resolver nomes, o Edge nunca resolverá o _sipfederationtls. \<seudomínio\> registro DNS, que é necessário para o fluxo de chamadas. Nesse caso, a Microsoft recomenda que você forneça um servidor DNS na interface externa Edge para resolver pesquisas de nomes de Internet, e cada componente de borda deve usar um arquivo HOST para resolver outros nomes de componentes do conector de nuvem para endereços IP.

> [!NOTE]
> Por motivos de segurança, recomendamos que você não aponte o servidor DNS do conector de nuvem para servidores internos no domínio de produção para resolução de nomes.

### <a name="determine-deployment-parameters"></a>Determinar parâmetros de implantação
<a name="BKMK_SiteParams"> </a>

Primeiramente, você deve definir os seguintes parâmetros de implantação comuns:


|**Item**|**Descrição**|**Observações**|
|:-----|:-----|:-----|
|Domínios SIP  <br/> |URIS SIP em uso pelos usuários da empresa. Forneça todos as domínios SIP que serão atendidos por essa implantação. É possível ter mais de um domínio SIP.  <br/> ||
|Número de sites PSTN  <br/> |O número de sites PSTN que você precisa implantar.  <br/> ||

Para cada site PSTN que você planeja implantar, será necessário coletar as seguintes informações antes de iniciar a implantação. Você deve fornecer estas informações quando atualizar o arquivo CloudConnector.ini.

Ao configurar informações de gateway, lembre-se do seguinte:

- Se houver apenas um gateway, remova a seção do arquivo .ini para o segundo gateway. Se houver mais de dois gateways, siga o formato existente para adicionar novos.

- Verifique se o endereço IP e a porta do(s) gateway(s) estão corretos.

- Para dar suporte a alta disponibilidade no nível do gateway PSTN, mantenha o gateway secundário ou adicione gateways.

(Opcional) Para limitar os números de chamadas de saída, atualize o valor LocalRoute.



|**Parâmetros do site**|**Descrição**|**Observações**|
|:-----|:-----|:-----|
|Nome de domínio da máquina virtual  <br/> |Nome de domínio dos componentes internos do conector de nuvem. Esse domínio precisa ser diferente do domínio de produção. O nome precisa ser o mesmo em todos os dispositivos do Cloud Connector.  <br/> Nome no arquivo. ini: "VirtualMachineDomain"  <br/> |.domínio local é o preferencial.   <br/> |
|Nome do controlador de domínio do conector de nuvem  <br/> |Nome do controlador de domínio   <br/> Nome no arquivo. ini: "NomeDoServidor"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|Máscara de sub-rede/IP do controlador de domínio do conector do Cloud  <br/> |Endereço IP do controlador de domínio   <br/> Nome no arquivo. ini: "IP"  <br/> ||
|FQDNs do serviço online do O365  <br/> |Deve ser o padrão na maioria dos casos para a instância do O365 em todo o mundo.  <br/> Nome no arquivo. ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nome do site do Skype for Business; por exemplo, Seattle.  <br/> Nome no arquivo. ini: "SiteName"  <br/> Para a versão 1.4.1 e posterior, o nome do site deve ser diferente para cada site, e o nome deve corresponder ao site PSTN, se existir, definido no Office 365. Note que os sites PSTN serão criados automaticamente ao registrar o primeiro dispositivo em um site.  <br/> ||
|HardwareType  <br/> Versão 1.4.1 e posterior  <br/> |Tipo de hardware. O valor padrão é Normal. Você também pode definir como Mínimo.  <br/> ||
|Código do país  <br/> |Código do país para discagem.  <br/> Nome no arquivo. ini: "CountryCode"  <br/> ||
|Cidade  <br/> |Cidade (opcional).  <br/> Nome no arquivo. ini: "cidade"  <br/> ||
|Estado  <br/> |Estado (opcional).  <br/> Nome no arquivo. ini: "estado"  <br/> ||
|Endereço IP da VM Base  <br/> |O endereço IP da VM de base temporária que será usada para criar o VHDX para todas as máquinas virtuais do conector de nuvem. Esse IP precisa estar na mesma sub-rede da rede corporativa de perímetro definida na próxima etapa e requer acesso à Internet. Defina o gateway padrão corporativo e o DNS que pode ser roteado para a Internet.  <br/> Nome no arquivo. ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Versão 1.4.1 e posterior  <br/> |O endereço do Windows Server Update Services (WSUS); um servidor de intranet para hospedar atualizações do Microsoft Update.  <br/> Você pode deixar em branco, se o WSUS não for necessário.   <br/> ||
|Máscara de sub-rede para rede interna  <br/> |O Cloud Connector configura uma rede IP para comunicação interna entre componentes do conector de nuvem. A borda também precisa ser conectada a outra sub-rede que permita conexão com a Internet.  <br/> Nome no arquivo. ini: "CorpnetIPPrefixLength" em "parâmetros para um pool de redes VM"  <br/> ||
|Máscara de subrede para rede externa   <br/> |Para a rede externa do componente de Borda.  <br/> Nome no arquivo. ini: "InternetIPPrefix" em "parâmetros para um pool de redes VM"  <br/> ||
|Nome do comutador para rede interna  <br/> |Nome para a opção que será usada para a rede do conector de nuvem interna.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "CorpnetSwitchName" em "parâmetros para um pool de redes VM  <br/> ||
|Nome do comutador para rede externa  <br/> |Nome para a opção que será usada para a rede do conector de nuvem externo.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "InternetSwitchName" em "parâmetros para um pool de redes VM  <br/> ||
|Gateway Padrão para rede interna  <br/> |Esse gateway deve fornecer acesso à Internet (a Internet também requer a configuração do servidor DNS) e será configurada em interfaces internas dos componentes do conector de nuvem.  <br/> Nome no arquivo. ini: "CorpnetDefaultGateway" em "parâmetros para um pool de redes VM  <br/> ||
|Gateway Padrão para a interface externa do componente de Borda  <br/> |Será configurado na interface externa do componente de Borda.  <br/> Nome no arquivo. ini: "InternetDefaultGateway" em "parâmetros para um pool de redes VM  <br/> ||
|Servidor DNS para rede interna  <br/> |Será configurado na interface interna da VM temporária. Deve fornecer uma resolução de nome para nomes da Internet. Sem o fornecimento de um servidor DNS, a conexão com a Internet apresentará falha e a implantação não será concluída.  <br/> Nome no arquivo. ini: "CorpnetDNSIPAddress" em "parâmetros para um pool de redes VM  <br/> ||
|Servidor DNS para a interface externa do componente de Borda  <br/> |Será configurado na interface externa de Borda.  <br/> Nome no arquivo. ini: "InternetDNSIPAddress" em "parâmetros para um pool de redes VM  <br/> ||
|Nome da central de gerenciamento  <br/> |A opção de gerenciamento é uma opção temporária que será criada automaticamente e que será usada para a configuração do conector de nuvem durante a implantação. Ele será desconectado automaticamente após a implantação. Ele deve ser uma sub-rede diferente das outras redes usadas no conector de nuvem.  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "ManagementSwitchName" em "parâmetros para um pool de redes VM  <br/> ||
|Endereço de sub-rede/máscara de sub-rede de gerenciamento  <br/> |A sub-rede de gerenciamento é uma sub-rede temporária que será criada automaticamente e que será usada para a configuração do conector de nuvem durante a implantação. Ela será removida automaticamente após a implantação. Ele deve ser uma sub-rede diferente das outras redes usadas no conector de nuvem.  <br/> Nomes no arquivo. ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" em "parâmetros para um pool de redes VM  <br/> ||
|Máquina do CMS (repositório central de gerenciamento)  <br/> |FQDN exclusivo utilizado para o Repositório de Gerenciamento Central (CMS). O nome do Domínio do AD será utilizado para gerar o FQDN.  <br/> Nome no arquivo. ini: "NomeDoServidor" em "parâmetros para o serviço de gerenciamento central principal  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> (Nome do Pool do CMS = Nome do Servidor)  <br/> |
|Endereço IP da máquina CMS  <br/> |Endereço IP do servidor CMS (interno na rede de perímetro).  <br/> Nome no arquivo INI: "IP" em "parâmetros para o serviço de gerenciamento central principal  <br/> ||
|Nome do Compartilhamento de Arquivo   <br/> |Nome do compartilhamento de arquivos a ser criado no servidor CMS para dados de replicação do Skype for Business (por exemplo, CmsFileStore).  <br/> Na maioria dos casos, o valor padrão sugerido pode ser usado.  <br/> Nome no arquivo. ini: "CmsFileStore" em "parâmetros para o serviço de gerenciamento central principal  <br/> ||
|Nome do pool de componentes de mediação  <br/> |Nome do Pool do componente de Mediação. Insira apenas o nome Netbios. O nome de domínio AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "PoolName" em "Parameters para um pool de servidores de mediação"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|Nome do componente de mediação  <br/> |Nome de Componente do componente de Mediação 1. Insira apenas o nome Netbios. O nome de domínio AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "NomeDoServidor" em "parâmetros para um pool de servidores de mediação"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|Endereço IP do computador do componente de mediação  <br/> |IP corpnet interno para componente de mediação (interno na rede de perímetro).  <br/> Nome no arquivo. ini: "IP" em "parâmetros para um pool de servidores de mediação"  <br/> ||
|Nome interno do pool de Borda  <br/> |Nome do Pool do componente de Borda. Insira apenas o nome Netbios. O nome de domínio AD será usado para gerar o FQDN.  <br/> Nome no arquivo. ini: "InternalPoolName" em "parâmetros para um pool de servidores de borda"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|Nome interno do Servidor de Borda  <br/> |Nome de Componente do componente de Borda. Insira apenas o nome Netbios. O nome de domínio AD será usado para gerar o FQDN.   <br/> Nome no arquivo. ini: "InternalServerName" em "parâmetros para um pool de servidores de borda"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|IP Interno de Servidor de Borda   <br/> |Componente de IP de rede de perímetro interno para se comunicar com outros componentes do conector de nuvem.  <br/> Nome no arquivo. ini: "InternalServerIPs" em "parâmetros para um pool de servidores de borda"  <br/> ||
|Nome externo do pool de acesso  <br/> |Nome da Borda de Acesso; por exemplo, AP. Esse nome deve corresponder ao nome fornecido para o certificado SSL. Insira apenas o nome Netbios. O nome do Domínio SIP será usado para gerar o FQDN. Um nome de pool externo será usado para todos os componentes de borda do pool. Um pool de acesso de borda é necessário para o site PSTN.  <br/> Nome no arquivo. ini: "ExternalSIPPoolName" em "parâmetros para um pool de servidores de borda"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> "SIP" é reservado e, portanto, não pode ser usado como o nome.  <br/> O nome FQDN gerado deve corresponder ao nome fornecido para o certificado SSL.   <br/> |
|IP externo de borda de acesso  <br/> |IP externo do componente Edge-IP público se não houver NAT disponível ou IP traduzido (especifique os dois endereços, se mapeado).  <br/> Nome no arquivo. ini: "ExternalSIPIPs" em "parâmetros para um pool de servidores de borda"  <br/> ||
|Nome de Retransmissão de Mídia  <br/> |Nome da Borda de Media Relay para Áudio e Vídeo; por exemplo, MR. Um nome de pool externo será utilizado para todos os componentes de Borda em um pool. Um pool de retransmissão de mídia de borda é necessário por site PSTN.  <br/> Nome no arquivo. ini: "ExternalMRFQDNPoolName" em "parâmetros para um pool de servidores de borda"  <br/> |Deve conter 15 caracteres ou menos. Insira apenas o nome Netbios.  <br/> |
|IP externo da borda de retransmissão de mídia  <br/> |No momento, há suporte para apenas um IP, portanto, será usado o mesmo IP da Borda de Acesso, seja IP público ou mapeado (especifique ambos os endereços se mapeados). Pode ser o mesmo endereço do IP Externo do componente de Borda da Borda de Acesso. Observe que se a Borda estiver usando NAT, você também precisará especificar o valor do próximo parâmetro.  <br/> Nome no arquivo. ini: "ExternalMRIPs" em "parâmetros para um pool de servidores de borda"  <br/> ||
|IP externo da borda de retransmissão de mídia (se a borda estiver atrás do NAT)  <br/> |Se a sua Borda estiver usando NAT, você também precisará especificar o endereço público da dispositivo NAT.  <br/> Nome no arquivo. ini: "ExternalMRPublicIPs" em "parâmetros para um pool de servidores de borda"  <br/> ||
|Marca e modelo do gateway de voz 1  <br/> |Especifique a marca e o modelo do SBC/Gateway de voz. Observe que você pode conectar um dispositivo ou tronco SIP da lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Marca e modelo do gateway de voz 2 (copiar esta linha se você tiver mais de 2 gateways)  <br/> |Especifique a marca e o modelo do gateway de voz. Observe que você pode conectar um dispositivo da lista de dispositivos testados em [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Nome do gateway de voz 1  <br/> |Usado para gerar o FQDN do computador com Domínio do AD. É necessário se o TLS for usado entre o componente de Mediação e o Gateway de Voz. Se você não planeja usar o FQDN, por exemplo, o TLS não é necessário ou o gateway de voz não é compatível com o uso de FQDN (apenas IP), especifique.  <br/> ||
|Nome do gateway de voz 2 (copiar esta linha se você tiver mais de 2 gateways)  <br/> |Usado para gerar o FQDN da máquina com Domínio do AD. É necessário se o TLS for usado entre o componente de Mediação e o Gateway de Voz. Se você não planeja usar o FQDN, por exemplo, o TLS não é necessário ou o gateway de voz não é compatível com o uso de FQDN (apenas IP), especifique.  <br/> ||
|Endereço IP do gateway de voz 1  <br/> |Endereço IP do Gateway de Voz.  <br/> ||
|Endereço IP do gateway de voz 2 (copiar esta linha se você tiver mais de 2 gateways)  <br/> |Endereço IP do Gateway de Voz.  <br/> ||
|Porta do gateway de voz 1 porta # (copiar esta linha se você tiver mais de 2 gateways)  <br/> |Porta que o tronco SIP do Gateway de Voz escutará, por exemplo, 5060.  <br/> ||
|Porta do gateway de voz 2 #  <br/> |Porta que o tronco SIP do Gateway de Voz escutará, por exemplo, 5060.  <br/> ||
|Protocolo de gateway de voz 1 para tráfego SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocolo de gateway de voz 2 para tráfego SIP (copiar esta linha se você tiver mais de 2 gateways)  <br/> |TCP ou TLS.  <br/> ||
|Intervalo de porta de Mídia Externa para tráfego de/para componente de Borda  <br/> |Intervalo de portas TCP/UDP para tráfego de mídia de/para interface externa da borda. Deve sempre começar a partir de 50000. Consulte "portas e protocolos" para obter mais informações.  <br/> |50000 - 59 999  <br/> |
|Intervalo de porta de mídia para se comunicar com/do componente de mediação por meio do firewall interno  <br/> |Intervalo de portas UDP que o componente de mediação usará para se comunicar com clientes e gateways (recomendação de 4 portas por chamada).  <br/> ||
|Intervalo de porta de mídia para se comunicar com/do cliente Skype for Business por meio de firewall interno  <br/> |Para fins de planejamento, não pode ser alterado. As portas precisam ser abertas no firewall interno para se comunicar entre clientes do Skype for Business na rede interna e com o componente de mediação.  <br/> |50 000- 50 019  <br/> |
|Senha de Certificado Público  <br/> |Será fornecida no script.  <br/> ||
|Senha do Administrador do Modo de Segurança  <br/> Somente a versão 1.4.2  <br/> |Senha de administrador do modo de segurança para domínio interno do CC.  <br/> ||
|Senha de administrador do domínio do conector do Cloud  <br/> Somente a versão 1.4.2  <br/> |Senha do administrador do domínio do conector de nuvem (diferente do domínio de produção). Nome de Usuário é Administrador. Não é possível alterar o nome de usuário.  <br/> ||
|Senha de Administrador de Máquinas Virtuais  <br/> Somente a versão 1.4.2  <br/> |Usado para configurar a rede de gerenciamento durante a implantação.  <br/> Nome de Usuário é Administrador. Não é possível alterar o nome de usuário.   <br/> ||
|CABackupFile  <br/> Versão 2.0 e posterior  <br/> |Usado para salvar o serviço da autoridade de certificação do servidor do Active Directory em um arquivo durante a implantação de vários aparelhos em um site do conector de nuvem. Certifique-se de usar a mesma senha para todos os dispositivos em um site do Cloud Connector a fim de importar com êxito o arquivo de backup da AC no novo dispositivo adicionado.  <br/> ||
|CCEService  <br/> Versão 2.0 e posterior  <br/> |Usado para o serviço de Gerenciamento do Cloud Connector; precisa de acesso ao diretório de sites do Cloud Connector. Certifique-se de usar a mesma senha para todos os dispositivos dentro de um site do Cloud Connector.   <br/> ||
|Administração de locatários do Office 365  <br/> | O Cloud Connector utiliza a conta para atualização e gerenciamento de configurações de locatário do Cloud Connector: <br/>  Versão 2,0 e posterior: credenciais para uma conta dedicada do Office 365 com direitos de administrador do Skype for Business. <br/>  Versões anteriores à 2.0: credenciais para uma conta dedicada do Office 365 com os direitos de administrador global de locatários. <br/> ||
|Habilitar o suporte REFER  <br/> |Isso definirá se o suporte a SIP REFER está habilitado ou não na Configuração do Tronco de seu IP/PBX. O valor padrão é True. Se seu Gateway IP/PBX é compatível com o suporte REFER, deixe True. Caso contrário, o valor precisa ser alterado para False. Se você não tiver certeza de que o seu gateway é compatível com a opção consulte [gateways e PBXS IP qualificados](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versão 2.0 e posterior  <br/> |Com o valor padrão "true", se as chamadas de saída não forem atendidas pelo gateway dentro de 10 segundos, elas serão roteadas para o próximo gateway disponível; Se não houver troncos adicionais, a chamada será descartada automaticamente.  <br/> No entanto, em uma organização com redes e respostas de gateway lentas, ou quando o processo de estabelecimento de chamadas demora mais de 10 segundos, isso pode resultar em chamadas canceladas sem necessidade.  <br/> Quando se faz chamadas para alguns países, por exemplo, os Emirados Árabes Unidos ou o Afeganistão, o processo de estabelecimento de chamada pode levar mais de 10 segundos. Você precisará alterar o valor para False se encontrar problemas semelhantes. Não se esqueça de alterar a configuração correspondente no SBC ou no Gateway conectado.  <br/> O valor pode ser True ou False. O padrão é True.  <br/> ||
|ForwardCallHistory  <br/> Versão 2.0 e posterior  <br/> | Utiliza-se esse parâmetro para a ativação dos cabeçalhos SIP que são usados para relatar o chamador inicial em cenários de Toque simultâneo, Encaminhamento de chamadas e Transferência de chamadas. Definir o parâmetro como True ativará dois cabeçalhos SIP:<br/>  Informações do Histórico <br/>  Mencionado por <br/>  O cabeçalho histórico-informações é usado para redirecionar solicitações SIP e "fornecer (s) um mecanismo padrão para capturar as informações do histórico de solicitações para habilitar uma ampla variedade de serviços para redes e usuários finais" ([RFC 4244-seção 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Para as interfaces de tronco do Cloud Connector, isso é usado em cenários de Toque simultâneo e Encaminhamento de chamadas.  <br/>  O valor pode ser True ou False. O padrão é False.<br/> ||
|Encaminhamento PAI  <br/> Versão 2.0 e posteriores  <br/> |A PAI é uma extensão privada para o SIP que permite aos servidores SIP declarar a identidade dos usuários autenticados. Para o provedor de tronco SIP, a PAI pode ser usada para fins de cobrança caso os cabeçalhos Informações do Histórico e Mencionado por não estejam presentes. Quando encaminhar P – a identidade declarada está habilitada na configuração, o servidor de mediação encaminhará cabeçalhos PAI com o URI do SIP &amp; Tel do conector de nuvem para o tronco SIP. O servidor de mediação encaminhará cabeçalhos PAI com &amp; os números E. 164 de URI de Tel somente recebidos no tronco SIP para o conector de nuvem. O Servidor de Mediação também enviará quaisquer cabeçalhos de Privacidade recebidos em qualquer direção. Se a solicitação SIP enviada pelo servidor de mediação incluir um cabeçalho de privacidade do formulário-"privacidade: ID" em conjunto com o cabeçalho PAI, a identidade declarada deve ser mantida em particular fora do domínio de confiabilidade da rede.  <br/> O valor pode ser True ou False. O padrão é False.  <br/> ||

### <a name="certificate-requirements"></a>Requisitos de certificado
<a name="BKMK_Certs"> </a>

Cada componente de Borda requer um certificado de uma autoridade de certificação pública. Os certificados devem ter uma chave privada exportável para cópia entre os componentes de Borda. Para atender aos requisitos de certificado, você deve decidir entre as seguintes opções e fornecer o Nome de Entidade (SN) e o Nome Alternativo de Entidade (SAN) para o certificado.

 **Se você tiver um único domínio SIP:**

- **Opção 1.** O Nome da Entidade deve conter o nome do pool que você atribuiu aos componentes de borda. Observe que o nome do requerente não pode ser sip.sipdomain.com porque esse nome é reservado para o componente do Skype for Business Edge online. A SAN deve conter sip.sipdomain.com e o nome do pool deborda de acesso:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opção 2. ** Se quiser usar um único certificado curinga em todos os servidores do pool de borda que você implantar, você poderá usar uma entrada de SAN de \*sipdomain.com em vez do nome do pool de bordas no certificado. O nome da entidade pode ser o nome do pool de Borda de acesso de quaisquer pools de Borda que você tenha implantado:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para SIP. \<sipdomain\>. com porque esse nome pertence à implantação do Office 365.

> [!NOTE]
> Se você quer usar um único certificado para todos os pools de Borda implantados em sua organização e não pode usar um certificado curinga como definido na opção 2, será necessário incluir o FQDN de todos os pools de Borda implantados no nome SAN no certificado. 

 **Se você tiver vários domínios SIP:**

Será preciso adicionar sip.sipdomain.com a cada domínio SIP e o nome dos pools de Borda de acesso por domínio (pode ser um pool físico, mas com nomes diferentes). Abaixo está um exemplo de entradas de SN e SAN em um cenário com vários domínios SIP:

- **Opção 1.** O nome do requerente deve conter o nome do pool que você atribuiu para componentes do Edge. Observe que o nome do requerente não pode ser sip.sipdomain.com porque esse nome é reservado para o componente do Skype for Business Edge online. A SAN deve conter sip.sipdomain.com e o nome do pool deborda de acesso:

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opção 2.</strong> Se quiser usar um único certificado curinga em todos os servidores do pool de borda que você implantar, você poderá usar uma entrada de SAN de \*sipdomain.com em vez do nome do pool de bordas no certificado. O nome da entidade pode ser o nome do pool de Borda de acesso de quaisquer pools de Borda que você tenha implantado:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Você não deve criar uma entrada DNS externa para SIP. \<sipdomain\>. com porque esse nome pertence à implantação do Office 365.

Para fins de implantação, é possível utilizar a tabela seguinte:

|**Opção**|**Descrição**|**Observações**|
|:-----|:-----|:-----|
|Qual opção você usará para sua implantação?  <br/> |Opção 1 ou 2  <br/> ||
|SN  <br/> |Forneça o SN para seu certificado  <br/> ||
|SAN  <br/> |Forneça o SAN para seu certificado  <br/> ||

Se você estiver usando o TLS entre o gateway e o Servidor de Mediação, será necessário obter o certificado raiz ou a cadeia de completa do certificado, para o certificado atribuído ao gateway.

## <a name="dial-plan-considerations"></a>Considerações sobre plano de discagem
<a name="BKMK_DailPlan"> </a>

O Cloud Connector requer a utilização de um plano de discagem online. Para obter mais informações sobre como configurar um plano de discagem online, consulte [o que são planos de discagem?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerações de Alta disponibilidade
<a name="BKMK_HA"> </a>

Ao implantar a edição do Cloud Connector para alta disponibilidade, implante pelo menos dois aparelhos que atuam como um backup. Cada aplicativo consiste em quatro componentes: Edge, mediação, repositório central de gerenciamento (CMS) e controlador de domínio.

Em geral, se um componente dentro de um aparelho ficar inoperante, o Cloud Connector Edition pode continuar a lidar com chamadas, mas você deve considerar o seguinte:

- **Considerações sobre componentes de Mediação, CMS e controlador de domínio**

    Assuma que o componente do CMS ou do controlador de domínio em um dispositivo cai. O dispositivo ainda pode manipular chamadas de entrada e de saída, mas se você reiniciar um componente de mediação quando o controlador de domínio ou o componente CMS não for alcançável, a mediação não funcionará. O mesmo se aplica para reiniciar o componente CMS quando o controlador de domínio está inoperante.

    **Recomendação:** Antes de reiniciar os componentes, verifique a disponibilidade dos outros componentes do aplicativo.

- **Considerações sobre componentes de Borda**

    Se o componente de Borda em um dispositivo não estiver disponível, o comportamento para chamadas de entrada e de saída será diferente como indicado a seguir:

  - **Chamada de saída**— uma chamada do seu usuário na Internet para uma rede PSTN.

    O mecanismo de distribuição de chamadas na nuvem identificará que um componente de Borda está inoperante e encaminhará todas as chamadas para outro dispositivo; portanto, a chamada de saída será realizada com sucesso.

  - **Chamada de entrada**– uma chamada da rede PSTN para um usuário que está em uma rede local ou na Internet.

     Se o componente de Borda do dispositivo que recebeu a chamada não estiver funcionando, as chamadas de entrada para esse dispositivo não terão êxito porque o componente de Mediação não poderá redirecionar a chamada para o componente de Borda no outro dispositivo.

    **Recomendação:** Tenha um sistema de monitoramento em vigor. Depois de identificar um mau funcionamento do componente Edge, desligue todos os componentes no aplicativo em que o componente Edge não está disponível.

## <a name="cloud-connector-media-flow"></a>Fluxo da mídia do Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Os diagramas a seguir descrevem o fluxo de uma chamada de entrada e de saída por meio do Cloud Connector Edition. São informações úteis para compreender como a conectividade é estabelecida.

No primeiro diagrama, um usuário interno estabelece uma chamada de saída da seguinte maneira:

1. Dave, um usuário hospedado online, mas que agora está na rede interna, faz uma chamada para um usuário PSTN externo.

2. Rotas de tráfego SIP para o Skype for Business online.

3. O Skype for Business online executa uma pesquisa de número inverso do número. A pesquisa de número reverso falha porque esse número não pertence a qualquer pessoa na organização do Skype for Business.

4. A chamada é encaminhada para o componente de Borda (SIP e fluxo de Mídia pela Borda Online, primeiramente; a Mídia, então, passará para o componente de Mediação por meio do firewall interno).

5. Se a rota existir, o componente de Borda retransmitirá o tráfego para o componente de Mediação na rede de perímetro.

6. O componente de Mediação envia o tráfego para o gateway de PSTN.

![Fluxo de mídia de saída para o conector de nuvem](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

No próximo diagrama, um usuário interno recebe uma chamada de entrada da seguinte maneira:

1. O gateway de PSTN recebe uma chamada para o usuário Dave, que está hospedado online, mas agora está na rede interna.

2. O tráfego SIP é roteado para o componente de Mediação.

3. O componente de mediação envia o tráfego SIP para o componente Edge e, em seguida, vai para o Skype for Business online.

4. O Skype for Business online executa uma pesquisa de número reverso do número e descobre que este é o usuário Dave.

5. A sinalização SIP vai para todos os pontos de presença de Dave.

6. O tráfego de mídia será estabelecido entre o gateway e o componente de Mediação e entre o componente de Mediação e o ponto de extremidade.

![Fluxo de mídia de entrada para o conector de nuvem](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoramento e solução de problemas
<a name="BKMK_Monitor"> </a>

O mecanismo de monitoramento e solução de problemas é instalado automaticamente com cada dispositivo do Cloud Connector. O mecanismo detecta os seguintes eventos:

- Uma ou mais máquinas virtuais de um dispositivo do Cloud Connector não estão conectadas a um comutador virtual interno ou da Internet.

- Uma ou mais máquinas virtuais de um dispositivo do Cloud Connector estão no status salvo ou parado.

- Serviços que não estão em execução.

  Se um dos seguintes eventos for detectado, o dispositivo do conector de nuvem inteiro será esgotado e marcado como offline para impedir a tentativa de estabelecer chamadas para um dispositivo que não está funcionando corretamente. Os recursos de recuperação automática do Cloud Connector restaurarão os serviços posteriormente e marcarão o dispositivo como online. Se a recuperação automática falhar por algum motivo, consulte [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

  - Na máquina virtual do Repositório de Gerenciamento Central: 

     - Agente Replicador Mestre do Skype for Business

     - Agente Replicador de Réplica do Skype for Business

  - Na máquina virtual do Servidor de Mediação:

     - Agente Replicador de Réplica do Skype for Business

     - Mediação do Skype for Business Server

  - Na Máquina Virtual do Servidor de Borda

     - Agente Replicador de Réplica do Skype for Business

     -  Borda de Acesso do Skype for Business Server

     - Borda de Áudio/Vídeo do Skype for Business Server

     - Autenticação de Áudio/Vídeo do Skype for Business Server

     - Borda de Webconferência do Skype for Business Server

- A regra de entrada do firewall do Windows para "CS RTCSRV" na Borda, "CS RTCMEDSRV" no Servidor de Mediação, está desabilitada.

O Cloud Connector 2.1 e versões posteriores dão suporte ao monitoramento do Cloud Connector usando o OMS (Operations Management Suite). Para obter mais informações, veja [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_MoreInfo"> </a>

Para obter mais informações, consulte o seguinte:

- [Soluções de Telefonia da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configurar e gerenciar o Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Plano para bypass de mídia no Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Implantar o bypass de mídia no Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


