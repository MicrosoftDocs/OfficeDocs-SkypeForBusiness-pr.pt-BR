---
title: Plano para IPv6 no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Implemente o IPv6 antes de instalar o Skype for Business Server.'
ms.openlocfilehash: dbb9977d8d11b130387eca9e87213c2760226142
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825241"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Plano para IPv6 no Skype for Business
 
**Resumo:** Implemente o IPv6 antes de instalar o Skype for Business Server.
  
O Skype for Business Server inclui suporte para endereços IP versão 6 (IPv6), juntamente com suporte contínuo a endereços IP versão 4 (IPv4). 

Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao crescente número de dispositivos em todo o mundo, os endereços IPv4 disponíveis estão sem saída. Por isso, muitos dispositivos novos estão passando a usar endereços IPv6. Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles. 

Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. A alteração na formatação e na funcionalidade para dispositivos que usam endereços IPv6 requer várias considerações sobre implantação e configuração na instalação do Skype for Business Server. 

Este tópico inclui as seguintes seções:
  
- [Visão geral dos tipos de endereço IP](ipv6.md#over)
    
- [Requisitos técnicos para IPv6](ipv6.md#tech)
    
- [Considerações sobre migração e coexistência para IPv6](ipv6.md#migration)
    
Se você determinar que vai usar endereços IPv6, consulte o artigo Configurar tipos de endereço [IP no Skype for Business.](ip-address-types.md)
  
## <a name="overview-of-ip-address-types"></a>Visão geral dos tipos de endereço IP
<a name="over"> </a>

Você tem três opções ao configurar endereços IP no Skype for Business Server. Você pode configurar o Skype for Business Server para dar suporte somente a IP versão 4 (IPv4), somente IP versão 6 (IPv6) ou uma combinação de ambos (conhecido como pilha dupla). Há vários problemas a considerar com cada tipo de configuração:
  
- **Somente IPv4** O IPv6 foi criado porque o mundo está ficando sem endereços IPv4. Por fim, o IPv6 terá suporte total em todo o mundo, mas, no momento, muitas empresas e dispositivos com os que sua empresa talvez precisem se comunicar ainda não suportam IPv6 e podem não ter suporte por algum tempo. Uma configuração somente IPv4 ajudará a garantir que a implementação do Skype for Business Server possa se comunicar com a maioria dos dispositivos existentes.
    
- **Somente IPv6** Por outro lado, uma implementação de IPv6 completa excluirá a comunicação com muitos dispositivos existentes.
    
- **Pilha Dual** Pilha dupla é uma rede em que os endereços IPv4 e IPv6 estão habilitados. Essa configuração é suportada no Skype for Business Server porque, na maioria dos casos, a transição de IPv4 completo para IPv6 completo levará vários anos.
    
As seções a seguir destacam a compatibilidade entre essas três configurações para vários recursos do Skype for Business Server.
  
> [!NOTE]
> A configuração de cliente ou servidor com IPv6 só tem suporte para fins de laboratório ou validação. A configuração somente IPv6 não é suportada na implantação de produção. 
  
### <a name="client-registration"></a>Registro do cliente
<a name="client"> </a>

|**Rede de ponto de extremidade do cliente**|**Rede do servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dupla  <br/> |
|Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |
|Pilha dupla  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Cliente Ponto a Ponto
<a name="peer"> </a>

As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após o registro bem-sucedido de ambos os clientes, as combinações a seguir são suportadas.
  
|**Ponto de extremidade 1 do cliente**|**Ponto de extremidade 2 do cliente**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dupla  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conferência
<a name="conf"> </a>

A conferência inclui áudio/vídeo, compartilhamento de aplicativos e aplicativos de colaboração de dados, como quadro de comunicação e compartilhamento de arquivos.
  
|**Rede de ponto de extremidade do cliente**|**Rede do servidor**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Pilha dupla  <br/> |
|Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |
|Pilha dupla  <br/> |IPv6  <br/> |
|IPv6  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Servidor de Mediação/PSTN
<a name="med"> </a>

O Skype for Business Server não suporta bypass de mídia para chamadas PSTN se o tráfego for por meio de uma interface IPv6. Se o bypass de mídia for necessário, recomendamos que o gateway PSTN seja configurado para IPv4. 
  
|**Interface primária 1**|**Interface PSTN (no Servidor de Mediação)**|**Configuração do gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |IPv6  <br/> |
   
1. A interface principal é a interface que se comunica com os componentes do Skype for Business Server.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicações ponto a ponto de usuário remoto
<a name="remote"> </a>

As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
  
|**Rede de usuários remotos**|**Servidor de borda (Borda externa)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração do Pool de Front-End e do Pool de Borda
<a name="FE_pool"> </a>

A tabela a seguir mostra a matriz de suporte entre o pool do Servidor Front-End e o pool do Servidor de Borda interno.
  
**Matriz de pool de front-end e pool de borda (borda interna)**

||**Pool de Borda: IPv4** <br/> |**Pool de Borda: Pilha Dual** <br/> |**Pool de Borda: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Front-End: IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-End: Pilha Dual** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-End: IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\* Use essa combinação somente em um ambiente de laboratório.
  
A tabela a seguir é uma matriz das combinações com suporte de interfaces de borda internas e externas.
  
**Matriz de Pool de Borda (Borda Interna) e Pool de Borda (Borda Externa)**

||**Pool de Borda (Borda Externa) : IPv4** <br/> |**Pool de Borda (Borda Externa): Pilha Dual** <br/> |**Pool de Borda (Borda Externa): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Borda (Borda Interna): IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Borda (Borda Interna): Pilha Dual** <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Borda (Borda Interna): IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\* Use essa combinação somente em um ambiente de laboratório.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado do Enterprise Voice para IPv6
<a name="Ent_V"> </a>

As implantações que incluem controle de admissão de chamada (CAC), Enhanced 9-1-1 (E9-1-1) ou bypass de mídia devem ser configuradas como somente IPv4 ou como uma implementação de pilha dual. Os pontos de extremidade que usam somente IPv6 não podem usar nenhum desses recursos.
  
> [!NOTE]
> Em uma implantação de pilha dupla, mesmo que um cliente do Skype for Business Server se conecte a um Skype for Business Server usando IPv6, o Skype for Business Server fará o melhor esforço para mapear um endereço IPv4 apropriado para dar suporte ao E9-1-1. 
  
Não há suporte para o serviço de Informações de Local com endereços IPv6.
  
A Unificação de Mensagens (UM) do Exchange não dá suporte a IPv6. Para a UM do Exchange, certifique-se de que a resolução dns não retorna um endereço IPv6. O uso de IPv6 pode causar falha quando as chamadas são enviadas para a caixa postal. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Suporte a outros recursos do Skype for Business Server para IPv6
<a name="Ent_V"> </a>

Além dos recursos e componentes mencionados anteriormente, o Skype for Business Server dá suporte a IPv6 para os seguintes recursos:
  
- **Chat Persistente**
    
    Configure o IPv6 para Chat Persistente usando o Construtor de Topologias. Para obter detalhes sobre como configurar o Chat Persistente, consulte a documentação implantando o Servidor de Chat Persistente.
    
- **Relatórios de QoE (Qualidade da Experiência) e cdr (registro de detalhes das chamada)**
    
    Os relatórios de monitoramento incluem o endereço IP conforme ele é armazenado no banco de dados do Monitoring Server, seja do tipo IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Se você planeja configurar o Skype for Business Server para IPv6, lembre-se dos seguintes requisitos:
  
- Para usar endereços IPv6 com o Skype for Business Server, você precisa criar registros DNS (sistema de nomes de domínio) para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa um registros de host AAAA (quad-A). Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6. Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.
    
    É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.
    
- Cada endereço IPv6 possui um escopo. Os três escopos que você pode usar para endereçamento IPv6 são endereços globais IPv6 (semelhantes a endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhantes aos intervalos de endereços IPv4 privados) e endereços locais de link IPv6 (semelhante a endereços IP privados automáticos no Windows Server para IPv4). Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo. 
    
> [!IMPORTANT]
> O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços atribuídos no nível do Windows Server e no nível do Skype for Business Server funcionem conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerações sobre migração e coexistência para IPv6
<a name="migration"> </a>

O IP versão 6 (IPv6) não é suportado no Lync Server 2010 ou no Office Communications Server. Para fins de piloto, você pode testar a coexistência de pilha dupla do Lync Server 2010 e do Skype for Business Server. Recomendamos que todos os pools de um determinado site central sejam atualizados para o Skype for Business Server antes de habilitar o IPv6 (rede de pilha dupla) para qualquer um dos pools. Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.
  
Os cenários a seguir são suportados durante a migração e coexistência:
  
- Pools do Skype for Business Server, do Lync Server 2013 e do Lync Server 2010 no modo IPv4, coexistindo com o Skype for Business Server no modo de pilha dupla.
    
- Pool do Skype for Business Server no modo somente IPv6, se o pool somente IPv6 estiver em silo.
    
## <a name="see-also"></a>Confira também
<a name="migration"> </a>

[Configurar tipos de endereço IP no Skype for Business](ip-address-types.md)

[Arquitetura de endereçamento ip versão 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de endereço unicast global IPv6](https://tools.ietf.org/html/rfc3587)
  
[Endereços unicast locais exclusivos](https://tools.ietf.org/html/rfc4193)
