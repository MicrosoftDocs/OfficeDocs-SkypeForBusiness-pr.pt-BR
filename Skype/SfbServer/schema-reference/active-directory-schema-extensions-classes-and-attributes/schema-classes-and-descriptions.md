---
title: Classes de esquema e descrições em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Esta seção descreve todas as classes de esquema usadas por Skype for Business Server .
ms.openlocfilehash: fbd3e3293cef72ba6592b86932639bd499464858
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829765"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Classes de esquema e descrições em Skype for Business Server
 
Esta seção descreve todas as classes de esquema usadas por Skype for Business Server . 
  
## <a name="schema-classes-and-descriptions"></a>Classes e descrições de esquema

|**Classe**|**Descrição**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange Destinatário de email de Unificação de Mensagens (UM).  <br/> |Essa classe auxiliar é compartilhada com Exchange UM.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta classe é um contêiner para vários contatos de aplicativo e não contém atributos próprios.  <br/> |Novo no Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta classe contém a entrada para o ponto de controle de serviço a uma instância de UCAS (serviços de aplicativos de comunicação unificados).  <br/> |Novo no Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Essa classe fornece uma associação de um pool específico ao serviço Application.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Essa classe auxiliar para msRTCSIP-ApplicationServer contém atributos que representam configurações para instâncias do serviço Application.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém todas as configurações relacionadas ao arquivamento.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta classe representa um único servidor de arquivamento de mensagens de instantâneas. Uma instância dessa classe é criada quando um computador é ativado como um servidor de arquivamento de mensagens de instantâneas, como um computador com o serviço de arquivamento de mensagens instantâneas instalado.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta classe é um contêiner para várias instâncias de diretórios de conferência e não contém atributos próprios.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta classe contém atributos que representam configurações de um diretório de conferência específico.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Ponto de controle de serviço genérico (SCP) para especificar o computador como um servidor executando Skype for Business Server.  <br/> |Novo no Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Essa classe auxiliar mantém as configurações de um Skype for Business Web App banco.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta classe contém os atributos que definem os domínios configurados do registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Esse contêiner de classe representa um único serviço de Borda de Acesso. Como um serviço de Borda de Acesso é implantado na rede de perímetro e os clientes geralmente não permitem o acesso dos Serviços de Domínio do Active Directory a partir da rede de perímetro, as instâncias do serviço de Borda de Acesso não são ingressadas na rede do Active Directory da intranet. Portanto, os Proxies de acesso não são automaticamente registrados no AD DS. O administrador deve configurar manualmente a existência de cada instância do serviço de Borda de Acesso no AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta classe auxiliar de msRTCSIP-MCU contém atributos que representam configurações de servidores de conferência.  <br/> |Novo no Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta classe auxiliar de msRTCSIP-MediationServer contém atributos que representam configurações de Servidores de Mediação.  <br/> |Novo no Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta classe auxiliar de msRTCSIP-Server contém atributos que representam configurações de servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém todas as configurações relacionadas à federação.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Essa classe contém todas as configurações que se aplicam em uma implantação Skype for Business Server de dados.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Essa classe representa uma única política de reunião Office Communications Server.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |O objeto de configuração da topologia global local.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Container para manter os objetos de configuração da topologia global.  <br/> |Novo no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta classe é um contêiner que representa uma instância de uma regra de normalização de local.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Essa classe é criada pelo aplicativo Atendedor de Conferência e contém atributos usados para categorizar números de telefone de conferência por região.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta classe é um contêiner para várias instâncias de mapeamentos de contato de localização e não contém atributos próprios.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta classe é um contêiner que representa um perfil de localidade específico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta classe é um contêiner para vários perfis de localidade e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta classe é um contêiner para várias regras de normalização de local e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta classe representa um único servidor de conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta classe contém várias classes msRTCSIP-MCUFactory e não tem atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Essa classe é um contêiner que representa uma fábrica de servidor de conferência para um único tipo de mídia. Uma instância dessa classe é criada quando o primeiro servidor de conferência para este tipo e fornecedor  específicos é ativado.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta classe fornece uma associação de um pool específico com o respectivo Alocador de Servidores de Conferência.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta classe contém a entrada do ponto de controle de serviço de um Servidor de Mediação.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que representam configurações de reunião que podem ser definidas.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Contâiner que armazena as configurações de mobilidade global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Essa classe contém atributos que representam configurações para um único Servidor de Monitoramento.  <br/> |Novo no Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta classe é um contêiner que representa uma instância de uma rota de custo mínimo para um gateway ou um conjunto de gateways. Essa informação é usada por todos os pools Enterprise ou servidores executando o Standard Edition para rotear chamadas de saída à rede telefônica pública comutada (PSTN) da maneira mais econômica.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta classe é um contêiner para várias rotas econômicas e não contém atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleto)  <br/> |Essa classe contém várias classes de política do Lync Server e não tem atributos em si.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Essa classe representa um único pool de Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Essa classe contém vários Skype for Business Server pools e não tem atributos em si.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Esta classe representa o ponto de controle de serviço de um pool. Os usuários hospedados em um pool têm o seu ponto de atributo msRTCSIP-PrimaryHomeServer a uma instância desta classe.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Contâiner que armazena as configurações de presença global.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que representam configurações de usuário mantidas pelos servidores do registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta classe é um contêiner que representa uma instância de uso de uma rota telefônica. Uma classe de rota de uso telefônica consiste em um campo de atributo e um campo de descrição. O campo de atributo define um tipo de uso. O campo da descrição permite que os administradores descrever o uso para este atributo na rota telefônica.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-RouteUsage e não tem atributos próprios.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que limitam e controlam o escopo dos resultados da pesquisa.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Essa classe representa um único servidor em execução Skype for Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta classe contém o contêiner de configurações globais e os objetos msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta classe contém atributos que representam configurações de um único servidor de conferência confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-TrustedMCU e não tem atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta classe contém várias classes msRTCSIP-TrustedProxy e não tem atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Essa classe é um contêiner que representa um servidor executando o servidor Proxy. Uma instância desta classe é criada ao ativar um novo servidor de Proxy em um computador associado ao AD DS.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta classe contém atributos que representam configurações de um único servidor confiável.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta classe é um contêiner que representa um serviço confiável que é roteável usando um URI de operador usuário de encaminhamento global (GRUU). Uma instância dessa classe é criada quando um novo servidor confiável por Skype for Business Server é ativado. O servidor confiáve deve ser associado a um domínio Active Directory.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta classe é um contêiner para vários servidores GRUU e não contém atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta classe contém atributos que representam as configurações de um componente da web confiável.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta classe contém várias instâncias da classe msRTCSIP-TrustedWebComponentServer e não tem atributos próprios.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos relacionados à comunicação unificada.  <br/> |Obsoleto no Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Esta classe contém o ponto de controle do serviço IIS (Internet Information Server). Ele identifica um servidor como um servidor de componentes web.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta classe fornece uma associação de um pool específico com os componentes web que ele usará.  <br/> |Novo no Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta classe auxiliar de msRTCSIP-WebComponents contém atributos que representam configurações de componentes web.  <br/> |Novo no Communications Server 2007.  <br/> |
   

