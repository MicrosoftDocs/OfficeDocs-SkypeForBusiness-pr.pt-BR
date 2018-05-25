---
title: Planejamento para IPv6 no Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumo: Implemente IPv6 antes de instalar Skype para Business Server 2015.'
ms.openlocfilehash: 4bd7a76e6b55b0b09cf0be469cb84c3d6384f109
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planejamento para IPv6 no Skype for Business
 
**Resumo:** Implemente o IPv6 antes de instalar Skype para Business Server 2015.
  
Skype para Business Server inclui o suporte para IP versão 6 (IPv6) endereços, juntamente com o suporte contínuo de IP versão 4 (IPv4) endereços. 

Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número crescente de dispositivos em todo o mundo, os endereços IPv4 disponíveis executaram check-out. Dessa forma, muitos novos dispositivos estejam mudando para usar endereços IPv6. Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32 bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles. 

Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. A alteração na formatação e funcionalidade para dispositivos que usam os endereços IPv6 requer várias considerações de implantação e configuração no seu Skype para instalação do servidor de negócios. 

Este tópico inclui as seguintes seções:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Se você determinar que você usará endereços IPv6, consulte o artigo de [tipos de endereço de IP configurar no Skype para negócios](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Visão geral dos tipos de endereço IP
<a name="over"> </a>

Você tem três opções ao configurar endereços IP no Skype para Business Server. Você pode configurar Skype para Business Server com suporte para IP versão 4 (IPv4), somente IP versão 6 (IPv6), ou uma combinação de ambos (conhecida como uma pilha dupla). Vários problemas devem ser considerados para cada tipo de configuração:
  
- **Apenas IPv4** IPv6 foi criado porque o mundo está ficando sem endereços IPv4. No fim das contas, o IPv6 será completamente suportado em todo o mundo, mas no momento, várias empresas e dispositivos aos quais sua empresa pode precisar se comunicar ainda não oferecem suporte ao IPv6, e poderão não oferecer por algum tempo. Uma configuração apenas IPv4 ajudará a garantir que sua Skype para implementação da Business Server pode se comunicar com a maioria dos dispositivos existentes.
    
- **Somente IPv6** Por outro lado, uma implementação completamente IPv6 excluirá a comunicação com vários dispositivos existentes.
    
- **Pilha dupla** Pilha dupla é uma rede onde os endereços IPv4 e IPv6 estão habilitados. Essa configuração é suportada no Skype para Business Server porque na maioria dos casos, a transição de IPv4 completo para full-IPv6 levará alguns anos.
    
As seções a seguir destacam a compatibilidade entre essas três configurações Skype vários recursos do Business Server.
  
> [!NOTE]
> Configuração de cliente ou servidor com somente IPv6 é suportada apenas para fins de validação ou utilização em laboratório. A configuração somente IPv6 não é suportada na implantação de produção. 
  
### <a name="client-registration"></a>Registro de cliente
<a name="client"> </a>

|**Rede de ponto de extremidade do cliente**|**Rede de servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Cliente ponto a ponto
<a name="peer"> </a>

As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após o registro bem sucedido de ambos os clientes, as combinações a seguir são suportadas.
  
|**Ponto de extremidade do cliente 1**|**Ponto de extremidade do cliente 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conferência
<a name="conf"> </a>

As conferências incluem áudio/vídeo, compartilhamento de aplicativos e colaboração de dados, como uso de quadro de comunicações e compartilhamento de arquivos.
  
|**Rede de ponto de extremidade do cliente**|**Rede de servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Servidor de Mediação/PSTN
<a name="med"> </a>

Skype para Business Server não suporta bypass de mídia para telefônica pública comutada (PSTN) de rede chamadas se o tráfego estiver através de uma interface de IPv6. Se o desvio de mídia é necessário, recomendamos que o gateway PSTN seja configurado para IPv4. 
  
|**Interface principal 1**|**Interface PSTN (no servidor de mediação)**|**Configuração do gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |IPv6  <br/> |
   
1. A interface principal é o que se comunica com o Skype para componentes de servidor de negócios.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicações ponto a ponto de usuário remoto
<a name="remote"> </a>

As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
  
|**Rede de usuários remotos**|**Servidor de borda (borda externa)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração do pool de Front-Ends e do pool do Servidor de Borda
<a name="FE_pool"> </a>

A tabela a seguir mostra a matriz de suporte entre o pool do servidor Front-End e pool de servidores de borda interno.
  
**Matriz de (borda interna) do Pool de borda e de Pool de Front-End**

||**Pool de borda: IPv4** <br/> |**Pool de borda: Pilha dual** <br/> |**Pool de borda: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Front-Ends: IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-Ends: Pilha dual** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-Ends: IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\*Use essa combinação somente em um ambiente de laboratório.
  
A tabela a seguir descreve a matriz de combinações suportadas das interfaces de borda interna e externa.
  
**Pool de borda (borda interna) e borda (borda externa) matriz do pool**

||**Pool de borda (Borda externa): IPv4** <br/> |**Pool de borda (Borda externa): Pilha dual** <br/> |**Pool de borda (Borda externa): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de borda (Borda interna): IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de borda (Borda interna): Pilha dual** <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de borda (Borda interna): IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\*Use essa combinação somente em um ambiente de laboratório.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado do Enterprise Voice para IPv6
<a name="Ent_V"> </a>

Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou passagem livre de mídia devem ser configurados como implementações somente IPv4 ou de pilha dual. Pontos de extremidade usando apenas IPv6 não podem usar nenhum desses recursos.
  
> [!NOTE]
> Em uma implantação de pilha dupla, mesmo se um Skype para cliente Business Server se conecta a um Skype para Business Server usando o IPv6, Skype para Business Server fará um melhor esforço para mapear um endereço IPv4 apropriado para suportar o E9-1-1. 
  
Serviço de informações de local com endereços IPv6 não é suportado.
  
O Unified Messaging (UM) do Exchange não suporta IPv6. Para o UM do Exchange, certifique-se de que a resolução do DNS não retorna um endereço IPv6. A utilização de IPv6 pode provocar falhas ao enviar chamadas para correios de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Outro Skype para suporte de recurso do servidor de negócios para IPv6
<a name="Ent_V"> </a>

Além dos recursos e componentes mencionados anteriormente, Skype para Business Server oferece suporte a IPv6 para os seguintes recursos:
  
- **Chat Persistente**
    
    Configurar o IPv6 para o Chat persistente usando o construtor de topologia. Para obter detalhes sobre a configuração de Chat persistente, consulte a documentação de implantação do servidor de Chat persistente.
    
- **Relatórios de CDR (registro de detalhes de chamada) e QoE (Qualidade de experiência)**
    
    Os relatórios de monitoramento incluem o endereço IP conforme é armazenado no banco de dados do Servidor de Monitoramento, independente de ser do tipo IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Se você planeja configurar Skype para Business Server para IPv6, lembre-se os seguintes requisitos:
  
- Para usar endereços IPv6 com Skype para Business Server, você precisará criar sistema de nomes de domínio (DNS) registra para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa um registros de host AAAA (quad-A). Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6. Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.
    
    É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.
    
- Cada endereço IPv6 possui um escopo. Os três escopos que você pode usar para o endereçamento IPv6 são endereços IPv6 globais (semelhantes aos endereços IPv4 públicos), exclusivo locais endereços IPv6 (semelhantes aos intervalos de endereços IPv4 privados) e endereços IPv6 de link local (semelhantes ao automáticos endereços IP privados em Windows Server para IPv4). Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo. 
    
> [!IMPORTANT]
> IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe da rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribuir no nível do Windows Server e no Skype para nível Business Server funcionam conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerações de migração e de coexistência para IPv6
<a name="migration"> </a>

IP versão 6 (IPv6) não é suportado no Lync Server 2010 ou o Office Communications Server. Para fins de teste-piloto, você pode testar o Lync Server 2010 e do Skype para coexistência de pilha dupla Business Server. Recomendamos que todos os pools para um determinado site central são atualizados para Skype para Business Server antes de habilitar IPv6 (rede de pilha dupla) para qualquer um dos pools. Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.
  
Os cenários a seguir são suportados durante a migração e coexistência:
  
- Skype para pools Business Server, Lync Server 2013 e Lync Server 2010 em modo IPv4, coexistindo com o Skype para Business Server no modo de pilha dupla.
    
- Skype para pool de servidores de negócios no modo apenas IPv6, se o pool apenas IPv6 estiver em silo.
    
## <a name="see-also"></a>Ver também
<a name="migration"> </a>

#### 

[Configurar tipos de endereço IP no Skype para negócios](ip-address-types.md)

[Arquitetura de endereçamento do IP versão 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de endereço Unicast Global de IPv6](https://tools.ietf.org/html/rfc3587)
  
[Endereços de Unicast IPv6 locais exclusivo](https://tools.ietf.org/html/rfc4193)

