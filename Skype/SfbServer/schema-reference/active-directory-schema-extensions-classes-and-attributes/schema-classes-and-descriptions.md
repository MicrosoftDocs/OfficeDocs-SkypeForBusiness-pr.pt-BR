---
title: Descrições e classes de esquema no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Esta seção descreve todas as classes de esquema usadas pelo Skype for Business Server.
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296592"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Descrições e classes de esquema no Skype for Business Server
 
Esta seção descreve todas as classes de esquema usadas pelo Skype for Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Classes e descrições de esquema

|**Classe**|**Descrição**|**Comentários**|
|:-----|:-----|:-----|
|E-mail-destinatário  <br/> |Destinatário de email do Exchange Unified Messaging (UM).  <br/> |Essa classe auxiliar é compartilhada com o Exchange UM.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Essa classe é um contêiner para vários contatos de aplicativo e não contém nenhum próprio atributo.  <br/> |Novo no Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Essa classe contém a entrada para o ponto de controle de serviço para uma instância de serviços de aplicativos de comunicação unificada (UCAS).  <br/> |Novo no Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Essa classe fornece uma associação de um pool específico ao seu serviço de aplicativo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta classe auxiliar para msRTCSIP-ApplicationServer mantém atributos representando configurações para instâncias do serviço de aplicativo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-arquivo morto (obsoleto)  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer armazena todas as configurações relacionadas ao arquivamento.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Essa classe representa um único servidor de arquivamento de mensagens instantâneas. Uma instância dessa classe é criada quando um computador é ativado como um servidor de arquivamento de mensagens instantâneas, como um computador com o serviço de arquivamento de mensagens instantâneas instalado.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Essa classe é um contêiner para várias instâncias de diretórios de conferência e não contém nenhum próprio atributo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Essa classe contém atributos que representam as configurações de um diretório de conferência específico.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Ponto de controle de serviço genérico (SCP) para especificar o computador como um servidor que executa o Skype for Business Server.  <br/> |Novo no Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Essa classe auxiliar mantém as configurações para um banco do Skype for Business Web App.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-domínio  <br/> |Essa classe contém atributos que definem os domínios configurados do registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Esse contêiner de classe representa um único serviço de borda de acesso. Como um serviço de borda de acesso é implantado na rede de perímetro e os clientes geralmente não permitem o acesso dos serviços de domínio Active Directory da rede de perímetro, as instâncias do serviço de borda de acesso não estão associadas à rede do Active Directory da intranet. Portanto, os proxies de acesso não são registrados automaticamente no AD DS. O administrador deve configurar manualmente a existência de cada instância do serviço de borda do Access no AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta classe auxiliar para msRTCSIP-MCU armazena atributos que representam configurações para servidores de conferência.  <br/> |Novo no Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta classe auxiliar para msRTCSIP-MediationServer mantém atributos representando configurações para servidores de mediação.  <br/> |Novo no Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Essa classe auxiliar para o msRTCSIP-Server armazena atributos que representam configurações para servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federação  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer armazena todas as configurações relacionadas à Federação.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Essa classe contém todas as configurações que se aplicam em toda a implantação do Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Essa classe representa uma única política de reunião do Office Communications Server.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |O objeto de configuração de topologia global local.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contêiner para armazenar objetos de configuração de topologia global.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Essa classe é um contêiner que representa uma instância de uma regra de normalização de localização.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Essa classe é criada pelo aplicativo atendedor de conferência e mantém os atributos usados para categorizar números de telefone de conferência por região.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Essa classe é um contêiner para várias instâncias de mapeamentos de contatos de local e não contém nenhum próprio atributo.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Essa classe é um contêiner que representa um perfil de local específico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Essa classe é um contêiner para vários perfis de localização e não contém nenhum próprio atributo.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Essa classe é um contêiner para várias regras de normalização locais e não contém nenhum próprio atributo.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Essa classe representa um único servidor de conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Essa classe contém várias classes msRTCSIP-MCUFactory e não tem nenhum próprio atributo.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Essa classe é um contêiner que representa uma fábrica de servidor de conferência para um único tipo de mídia. Uma instância dessa classe é criada quando o primeiro servidor de conferência para esse tipo e fornecedor específico é ativado.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Essa classe fornece uma associação de um pool específico à sua fábrica do servidor de conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Essa classe contém a entrada para o ponto de controle de serviço para um servidor de mediação.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP – reunião (obsoleto)  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que representam as configurações de reunião configuráveis.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP – mobilidade  <br/> |Contêiner que armazena as configurações de mobilidade global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Essa classe contém atributos que representam as configurações de um único servidor de monitoramento.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Essa classe é um contêiner que representa uma instância de uma rota de menor custo para um gateway ou conjunto de gateways. Essas informações são usadas por todos os pools ou servidores da empresa que executam o Standard Edition para direcionar chamadas feitas para a rede telefônica pública comutada (PSTN) da maneira mais econômica.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Essa classe é um contêiner para várias rotas de custo mínimo e não contém nenhum próprio atributo.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-políticas (obsoletas)  <br/> |Essa classe contém várias classes de política do Lync Server e não tem nenhum próprio atributo.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-pool  <br/> |Essa classe representa um único pool do Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Essa classe contém vários pools do Skype for Business Server e não tem nenhum próprio atributo.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Essa classe representa o ponto de controle pointservice do controle de serviço de um pool. Os usuários hospedados em um pool têm seus atributos msRTCSIP-PrimaryHomeServer apontam para uma instância dessa classe.  <br/> |-  <br/> |
|msRTCSIP-presença  <br/> |Contêiner que armazena as configurações de presença global.  <br/> |-  <br/> |
|msRTCSIP-registrador  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que representam as configurações de usuário mantidas pelos servidores de registradores SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Essa classe é um contêiner que representa uma instância de um uso de rota telefônica. Uma classe de uso de rota de telefone consiste em um campo de atributo e um campo de descrição. O campo Attribute define um tipo de uso. O campo Descrição permite que os administradores descrevam o uso para esse atributo na rota do telefone.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Essa classe contém várias instâncias da classe msRTCSIP-RouteUsage e não tem nenhum próprio atributo.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-pesquisa  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos que limitam e controlam o escopo dos resultados da pesquisa.  <br/> |-  <br/> |
|msRTCSIP-servidor  <br/> |Essa classe representa um único servidor que executa o Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-serviço  <br/> |Essa classe mantém o contêiner de configurações globais e os objetos msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Essa classe contém atributos que representam as configurações de um servidor de conferência confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Essa classe contém várias instâncias da classe msRTCSIP-TrustedMCU e não tem nenhum próprio atributo.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Essa classe contém várias classes msRTCSIP-TrustedProxy e não contém nenhum próprio atributo.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Essa classe é um contêiner que representa um servidor de proxy em execução. Uma instância dessa classe é criada ao ativar um novo servidor proxy em um computador associado ao AD DS.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Essa classe contém atributos que representam as configurações de um servidor confiável.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Essa classe é um contêiner que representa um serviço confiável que é roteável usando um endereço de URI (GRUU) do agente do usuário roteável globalmente. Uma instância dessa classe é criada quando um novo servidor que é confiável para o Skype for Business Server é ativado. Este servidor confiável deve estar associado a um domínio do Active Directory.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-Confiáveisservices  <br/> |Essa classe é um contêiner para vários servidores GRUU e não contém nenhum próprio atributo.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Essa classe contém atributos que representam as configurações para um componente da Web confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Essa classe contém várias instâncias da classe msRTCSIP-TrustedWebComponentServer e não tem nenhum próprio atributo.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta classe auxiliar para msRTCSIP-GlobalContainer mantém os atributos relacionados à comunicação unificada.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Essa classe mantém o ponto de controle pointservice do controle de serviço para o Internet Information Server (IIS). Ele identifica um servidor como um servidor de componentes Web.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Essa classe fornece uma associação de um pool específico para os componentes Web que o pool irá usar.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta classe auxiliar para msRTCSIP-WebComponents mantém atributos representando configurações para componentes Web.  <br/> |Novo no Communications Server 2007.  <br/> |
   

