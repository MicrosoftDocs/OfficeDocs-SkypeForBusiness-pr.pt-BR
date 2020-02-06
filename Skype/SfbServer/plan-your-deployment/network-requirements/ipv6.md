---
title: Planejamento para IPv6 no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumo: implemente o IPv6 antes de instalar o Skype for Business Server.'
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802071"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planejamento para IPv6 no Skype for Business
 
**Resumo:** Implemente o IPv6 antes de instalar o Skype for Business Server.
  
O Skype for Business Server inclui suporte para endereços IP versão 6 (IPv6), além do suporte contínuo a endereços IP versão 4 (IPv4). 

Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número cada vez maior de dispositivos em todo o mundo, os endereços IPv4 disponíveis têm sido executados. Por isso, muitos dispositivos novos estão migrando para o uso de endereços IPv6. Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles. 

Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. A alteração na formatação e na funcionalidade para dispositivos que usam endereços IPv6 requer várias considerações de implantação e configuração na instalação do Skype for Business Server. 

Este tópico inclui as seguintes seções:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Se você determinar que usará endereços IPv6, confira o artigo [Configurar tipos de endereços IP no Skype for Business](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Visão geral dos tipos de endereço IP
<a name="over"> </a>

Você tem três opções ao configurar endereços IP no Skype for Business Server. Você pode configurar o Skype for Business Server para dar suporte somente para IP versão 4 (IPv4), somente para IP versão 6 (IPv6) ou uma combinação de ambas (conhecida como pilha dupla). Vários problemas devem ser considerados para cada tipo de configuração:
  
- **Somente IPv4** O IPv6 foi criado porque o mundo está ficando sem endereços IPv4. No fim das contas, o IPv6 será completamente suportado em todo o mundo, mas no momento, várias empresas e dispositivos aos quais sua empresa pode precisar se comunicar ainda não oferecem suporte ao IPv6, e poderão não oferecer por algum tempo. Uma configuração somente IPv4 ajudará a garantir que a implementação do Skype for Business Server possa se comunicar com a maioria dos dispositivos existentes.
    
- **Somente IPv6** Por outro lado, uma implementação de IPv6 completa excluirá a comunicação com muitos dispositivos existentes.
    
- **Pilha dupla** Pilha dupla é uma rede onde ambos os endereços IPv4 e IPv6 estão habilitados. Essa configuração tem suporte no Skype for Business Server porque, na maioria dos casos, a transição de Full-IPv4 para Full-IPv6 levará vários anos.
    
As seções a seguir descrevem a compatibilidade entre essas três configurações para vários recursos do Skype for Business Server.
  
> [!NOTE]
> Configuração de cliente ou servidor com somente IPv6 é suportada apenas para fins de validação ou utilização em laboratório. A configuração somente IPv6 não é suportada na implantação de produção. 
  
### <a name="client-registration"></a>Registro de cliente
<a name="client"> </a>

|**Extremidade de rede de cliente**|**Rede de servidor**|
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
  
|**Extremidade de cliente 1**|**Extremidade de cliente 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dual  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conferência
<a name="conf"> </a>

As conferências incluem áudio/vídeo, compartilhamento de aplicativos e colaboração de dados, como uso de quadro de comunicações e compartilhamento de arquivos.
  
|**Extremidade de rede de cliente**|**Rede de servidor**|
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

O Skype for Business Server não oferece suporte a bypass de mídia para chamadas PSTN (rede telefônica pública comutada) se o tráfego for por meio de uma interface IPv6. Se o desvio de mídia é necessário, recomendamos que o gateway PSTN seja configurado para IPv4. 
  
|**Interface primária 1**|**Interface PSTN (no Servidor de Mediação)**|**Configuração do gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |IPv6  <br/> |
   
1. A interface principal é a interface que se comunica com os componentes do Skype for Business Server.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicações ponto a ponto de usuário remoto
<a name="remote"> </a>

As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
  
|**Rede de usuários remotos**|**Servidor de borda (Borda externa)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |IPv4  <br/> |
|Pilha dual  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |Pilha dual  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração do pool de Front-Ends e do pool do Servidor de Borda
<a name="FE_pool"> </a>

A tabela a seguir mostra a matriz de suporte entre o pool do servidor front-end e o pool do servidor de borda interna.
  
**Matriz do Pool de Front-Ends e do Pool de Borda (Borda interna)**

||**Pool de borda: IPv4** <br/> |**Pool de borda: Pilha dual** <br/> |**Pool de borda: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Front-Ends: IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-Ends: Pilha dual** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-Ends: IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\*Use essa combinação apenas em um ambiente de laboratório.
  
A tabela a seguir descreve a matriz de combinações suportadas das interfaces de borda interna e externa.
  
**Matriz do Pool de borda (Borda interna) e do Pool de borda (Borda externa)**

||**Pool de borda (Borda externa): IPv4** <br/> |**Pool de borda (Borda externa): Pilha dual** <br/> |**Pool de borda (Borda externa): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de borda (Borda interna): IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de borda (Borda interna): Pilha dual** <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de borda (Borda interna): IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\*Use essa combinação apenas em um ambiente de laboratório.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado do Enterprise Voice para IPv6
<a name="Ent_V"> </a>

Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou passagem livre de mídia devem ser configurados como implementações somente IPv4 ou de pilha dual. Pontos de extremidade usando apenas IPv6 não podem usar nenhum desses recursos.
  
> [!NOTE]
> Em uma implantação de pilha dupla, mesmo que um cliente do Skype for Business Server se conecte a um servidor do Skype for Business usando o IPv6, o Skype for Business Server fará um melhor esforço para mapear um endereço IPv4 apropriado para dar suporte a E9-1-1. 
  
Não há suporte para o serviço de informações de localização com endereços IPv6.
  
O Unified Messaging (UM) do Exchange não suporta IPv6. Para o UM do Exchange, certifique-se de que a resolução do DNS não retorna um endereço IPv6. A utilização de IPv6 pode provocar falhas ao enviar chamadas para correios de voz. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Outro recurso de suporte do Skype for Business Server para IPv6
<a name="Ent_V"> </a>

Além dos recursos e componentes mencionados anteriormente, o Skype for Business Server oferece suporte ao IPv6 para os seguintes recursos:
  
- **Chat Persistente**
    
    Você configura o IPv6 para chats persistentes usando o construtor de topologias. Para obter detalhes sobre como configurar o chat persistente, consulte a documentação implantando o servidor de chat persistente.
    
- **Relatórios de CDR (registro de detalhes de chamada) e QoE (Qualidade de experiência)**
    
    Os relatórios de monitoramento incluem o endereço IP conforme é armazenado no banco de dados do Servidor de Monitoramento, independente de ser do tipo IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Se você planeja configurar o Skype for Business Server para IPv6, tenha em mente os seguintes requisitos:
  
- Para usar endereços IPv6 com o Skype for Business Server, você precisa criar registros de sistema de nomes de domínio (DNS) para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa um registros de host AAAA (quad-A). Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6. Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.
    
    É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.
    
- Cada endereço IPv6 possui um escopo. Os três escopos que você pode usar para endereçamento IPv6 são endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), endereços locais exclusivos do IPv6 (semelhantes aos intervalos de endereços IPv4 particulares) e endereços de conexão local IPv6 (semelhantes a endereços IP privados particulares no Windows Server para IPv4). Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo. 
    
> [!IMPORTANT]
> O IPv6 é um tópico complexo e requer planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribuir no nível do servidor do Windows e no nível do servidor do Skype for Business funcionem conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerações de migração e de coexistência para IPv6
<a name="migration"> </a>

Não há suporte para IP versão 6 (IPv6) no Lync Server 2010 ou no Office Communications Server. Para fins de piloto, você pode testar o Lync Server 2010 e o Skype for Business Server de coexistência de duas pilhas. Recomendamos que todos os pools de um determinado site central sejam atualizados para o Skype for Business Server antes de habilitar o IPv6 (rede de pilha dupla) para qualquer um dos pools. Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.
  
Os cenários a seguir são suportados durante a migração e coexistência:
  
- O Skype for Business Server, o Lync Server 2013 e o Lync Server 2010 pools no modo IPv4, coexistente com o Skype for Business Server no modo de pilha dupla.
    
- Pool do Skype for Business Server no modo somente IPv6, se o pool somente IPv6 estiver em silo.
    
## <a name="see-also"></a>Confira também
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[Arquitetura de endereçamento de IP versão 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de endereço de difusão ponto a ponto global IPv6](https://tools.ietf.org/html/rfc3587)
  
[Endereços exclusivos de unicast IPv6 locais](https://tools.ietf.org/html/rfc4193)
