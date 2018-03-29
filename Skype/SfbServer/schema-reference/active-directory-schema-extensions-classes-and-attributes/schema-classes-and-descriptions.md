---
title: Classes de esquema e descrições Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Esta seção descreve todas as classes de esquema usadas pelo Skype para Business Server.
ms.openlocfilehash: 20d85e879bb9bfb040150423d47836b6e6803c37
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes de esquema e descrições Skype para Business Server
 
Esta seção descreve todas as classes de esquema usadas pelo Skype para Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Descrições e Classes de esquema

|**Classe**|**Descrição**|**Comentários**|
|:-----|:-----|:-----|
|Destinatário do email  <br/> |Destinatário de email do Exchange Unified Messaging (UM).  <br/> |Esta classe auxiliar é compartilhada com UM do Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta classe é um contêiner para vários contatos de aplicativo e não contém atributos próprios.  <br/> |Novo no Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta classe contém a entrada para o ponto de controle de serviço para uma instância de Unified Communications Application UCAS (serviços).  <br/> |Novo no Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Esta classe fornece uma associação de um pool específico com o seu serviço de aplicativo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta classe auxiliar para msRTCSIP-ApplicationServer contém atributos que representam configurações de instâncias do serviço do aplicativo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém todas as configurações relacionadas ao arquivamento.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta classe representa uma única servidor de arquivamento de mensagens de instantâneas. Uma instância desta classe é criada quando um computador é ativado como um servidor de mensagens instantâneas do arquivamento, como um computador com o serviço de arquivamento de mensagens instantâneas instalado.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta classe é um contêiner para várias instâncias de diretórios de conferência e não contém atributos próprios.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta classe contém atributos que representam configurações de um diretório de conferência específico.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|objetos msRTCSIP-ConnectionPoint  <br/> |Ponto de controle de serviço genérico (SCP) para especificar o computador como um servidor executando o Skype para Business Server.  <br/> |Novo no Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Esta classe auxiliar contém as configurações para um Skype para negócios Web App bank.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta classe contém atributos que definem os domínios configurados do registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Este contêiner de classe representa um único serviço de borda de acesso. Como um serviço de borda de acesso é implantado na rede de perímetro e os clientes geralmente não permitem acesso de serviços de domínio do Active Directory de rede de perímetro, instâncias de serviço de borda de acesso não são associadas à rede do Active Directory da intranet. Portanto, os Proxies de acesso não são automaticamente registrados no AD DS. O administrador deve configurar manualmente a existência de cada instância do serviço de borda de acesso no AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta classe auxiliar de msRTCSIP-MCU contém atributos que representam configurações de servidores de conferência.  <br/> |Novo no Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta classe auxiliar de msRTCSIP-mediationserver contém atributos que representam configurações de servidores de mediação.  <br/> |Novo no Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta classe auxiliar de msRTCSIP-Server contém atributos que representam configurações de servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém todas as configurações relacionadas à Federação.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Esta classe contém todas as configurações que se aplicam em uma Skype para implantação de servidor de negócios.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Esta classe representa uma única política de reunião do Office Communications Server.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |O objeto de configuração de topologia global local.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Recipiente para armazenar objetos de configuração de topologia global.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta classe é um contêiner que representa uma instância de uma regra de normalização de local.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Esta classe é criada pelo aplicativo Atendedor de conferência e retém os atributos usados para categorizar os números de telefone de conferência por região.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta classe é um contêiner para várias instâncias do local de mapeamentos de contato e não contém atributos próprios.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta classe é um contêiner que representa um perfil de localidade específico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta classe é um contêiner para vários perfis de localidade e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta classe é um contêiner para várias regras de normalização local e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta classe representa um único servidor de conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta classe contém várias classes msRTCSIP-MCUFactory e não tem atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Esta classe é um contêiner que representa um alocador de servidores de conferência para um único tipo de mídia. Uma instância desta classe é criada quando o primeiro servidor de conferência para este tipo e fornecedor específico é ativado.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta classe fornece uma associação de um pool específico com o respectivo alocador de servidores de conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta classe contém a entrada para o ponto de controle de serviço para um servidor de mediação.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém atributos que representam configurações de reunião configurável.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-mobilidade  <br/> |Contêiner que armazena as configurações de mobilidade global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Esta classe contém atributos que representam as configurações para um único servidor de monitoramento.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta classe é um contêiner que representa uma instância de uma rota mais barata para um gateway ou um conjunto de gateways. Essa informação é usada por todos os pools Enterprise ou servidores que executam o Standard Edition para rotear chamadas de saída para a rede telefônica pública comutada (PSTN) da maneira mais econômica.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta classe é um contêiner para várias rotas econômicas e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleto)  <br/> |Esta classe contém vários Lync Server classes de política e não tem quaisquer atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Esta classe representa um único Skype para pool de servidores de negócios.  <br/> |-  <br/> |
|msRTCSIP-Pools.  <br/> |Esta classe contém vários Skype para pools de servidor de negócios e não tem quaisquer atributos próprios.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Esta classe representa o ponto de controle de pointservice de controle de serviço de um pool. Os usuários hospedados em um pool tem msRTCSIP-PrimaryHomeServer atributo ponto para uma instância desta classe.  <br/> |-  <br/> |
|msRTCSIP-presença  <br/> |Contêiner que armazena as configurações de presença global.  <br/> |-  <br/> |
|msRTCSIP-registrador  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém atributos que representam configurações de usuário mantidas pelos servidores de registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta classe é um contêiner que representa uma instância de um uso de rota de telefone. Uma classe de uso de rota de telefone consiste em um campo de atributo e um campo de descrição. O campo de atributo define um tipo de uso. O campo de descrição permite que os administradores descrever o uso neste atributo no rota telefônica.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-RouteUsage e não tem quaisquer atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-pesquisa  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém atributos que limitam e controlam o escopo dos resultados da pesquisa.  <br/> |-  <br/> |
|msRTCSIP-servidor  <br/> |Esta classe representa um único servidor executando o Skype para Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta classe contém o contêiner de configurações globais e os objetos msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta classe contém atributos que representam configurações de um servidor de conferência confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-TrustedMCU e não tem quaisquer atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta classe contém várias classes msRTCSIP-TrustedProxy e não contém atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Esta classe é um contêiner que representa um servidor executando o servidor Proxy. Uma instância desta classe é criada quando ativar um novo servidor de Proxy em um computador associado ao AD DS.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta classe contém atributos que representam configurações de um servidor confiável.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta classe é um contêiner que representa um serviço confiável que seja roteável usando um endereço globalmente roteável usuário agente URI (GRUU). Uma instância desta classe é criada quando um novo servidor que é confiável pelo Skype para Business Server é ativado. Isso confiáveis server deve ser associado a um domínio do Active Directory.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta classe é um contêiner para vários servidores GRUU e não contém atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta classe contém atributos que representam as configurações para um componente web confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-TrustedWebComponentServer e não tem quaisquer atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-globalcontainer contém atributos relacionados à comunicação unificada.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Esta classe contém o ponto de controle de pointservice de controle de serviço para o servidor de informações da Internet (IIS). Identifica um servidor como um servidor de web components.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta classe fornece uma associação de um pool específico com os componentes web que usarão o pool.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta classe auxiliar de msRTCSIP-webcomponents contém atributos que representam configurações de componentes web.  <br/> |Novo no Communications Server 2007.  <br/> |
   

