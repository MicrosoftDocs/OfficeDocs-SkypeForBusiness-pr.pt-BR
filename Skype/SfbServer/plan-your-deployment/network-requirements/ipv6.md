---
title: Planejar IPv6 no Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumo: Implemente iPv6 antes de instalar Skype for Business Server.'
ms.openlocfilehash: 6126cd2211a2df0f0a24672d61cf11ce89ad23c7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770059"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planejar IPv6 no Skype for Business
 
**Resumo:** Implemente iPv6 antes de instalar Skype for Business Server.
  
Skype for Business Server inclui suporte para endereços IP versão 6 (IPv6), juntamente com o suporte contínuo de endereços IP versão 4 (IPv4). 

Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número crescente de dispositivos em todo o mundo, os endereços IPv4 disponíveis foram executados. Devido a isso, muitos novos dispositivos estão mudando para o uso de endereços IPv6. Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles. 

Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. A alteração na formatação e na funcionalidade para dispositivos que usam endereços IPv6 requer várias considerações de implantação e configuração em sua instalação Skype for Business Server. 

Este tópico inclui as seguintes seções:
  
- [Visão geral dos tipos de endereço IP](ipv6.md#over)
    
- [Requisitos técnicos para IPv6](ipv6.md#tech)
    
- [Considerações de migração e coexistência para IPv6](ipv6.md#migration)
    
Se você determinar que estará usando endereços IPv6, consulte o artigo Configurar tipos de [endereço IP Skype for Business.](ip-address-types.md)
  
## <a name="overview-of-ip-address-types"></a>Visão geral dos tipos de endereço IP
<a name="over"> </a>

Você tem três opções ao configurar endereços IP Skype for Business Server. Você pode configurar o Skype for Business Server para dar suporte apenas a IP versão 4 (IPv4), somente IP versão 6 (IPv6) ou uma combinação de ambos (conhecido como pilha dupla). Há vários problemas a considerar com cada tipo de configuração:
  
- **Somente IPv4** IPv6 foi criado porque o mundo está ficando sem endereços IPv4. Por fim, o IPv6 terá suporte total em todo o mundo, mas, neste momento, muitas empresas e dispositivos com os que sua empresa pode precisar se comunicar ainda não suportam o IPv6, e talvez não por algum tempo. Uma configuração somente IPv4 ajudará a garantir que sua implementação Skype for Business Server possa se comunicar com a maioria dos dispositivos existentes.
    
- **Somente IPv6** Por outro lado, uma implementação IPv6 completa excluirá a comunicação com muitos dispositivos existentes.
    
- **Pilha Dupla** Pilha dupla é uma rede onde os endereços IPv4 e IPv6 estão habilitados. Essa configuração é suportada no Skype for Business Server porque, na maioria dos casos, a transição de full-IPv4 para full-IPv6 levará vários anos.
    
As seções a seguir definem a compatibilidade entre essas três configurações para vários Skype for Business Server recursos.
  
> [!NOTE]
> A configuração de cliente ou servidor com IPv6 só é suportada para fins de laboratório ou validação. A configuração somente IPv6 não é suportada na implantação de produção. 
  
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
   
### <a name="peer-to-peer-client"></a>Cliente ponto a ponto
<a name="peer"> </a>

As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivo. Depois que ambos os clientes se registrarem com êxito, as seguintes combinações são suportadas.
  
|**Ponto de extremidade do cliente 1**|**Ponto de extremidade do cliente 2**|
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

Skype for Business Server não dá suporte a bypass de mídia para chamadas PSTN (rede telefônica pública comutado) se o tráfego estiver por meio de uma interface IPv6. Se o bypass de mídia for necessário, recomendamos que o gateway PSTN seja configurado para IPv4. 
  
|**Interface primária 1**|**Interface PSTN (no Servidor de Mediação)**|**Configuração de gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |IPv6  <br/> |
   
1. A interface principal é a interface que se comunica com os Skype for Business Server componentes.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicações ponto a ponto do usuário remoto
<a name="remote"> </a>

As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.
  
|**Rede de usuário remoto**|**Servidor de Borda (Borda externa)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |IPv4  <br/> |
|Pilha dupla  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |Pilha dupla  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração de Pool de Front-End e Pool de Borda
<a name="FE_pool"> </a>

A tabela a seguir mostra a matriz de suporte entre o pool do Servidor front-end e o pool interno do Servidor de Borda.
  
**Matriz de Pool de Front-End e Pool de Borda (Borda Interna)**

||**Pool de Borda: IPv4** <br/> |**Pool de Borda: Pilha Dupla** <br/> |**Pool de Borda: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Front-End: IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-End: Pilha Dupla** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Front-End: IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\* Use essa combinação somente em um ambiente de laboratório.
  
A tabela a seguir é uma matriz das combinações suportadas de interfaces de borda internas e externas.
  
**Matriz Pool de Borda (Borda Interna) e Pool de Borda (Borda Externa)**

||**Pool de Borda (Borda Externa) : IPv4** <br/> |**Pool de Borda (Borda Externa): Pilha Dupla** <br/> |**Pool de Borda (Borda Externa): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool de Borda (Borda Interna): IPv4** <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Borda (Borda Interna): Pilha Dupla** <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |
|**Pool de Borda (Borda Interna): IPv6** <br/> |Não  <br/> |Não  <br/> |Sim\*  <br/> |
   
\* Use essa combinação somente em um ambiente de laboratório.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado Enterprise Voice IPv6
<a name="Ent_V"> </a>

As implantações que incluem o controle de admissão de chamada (CAC), o Enhanced 9-1-1 (E9-1-1) ou o bypass de mídia devem ser configuradas como IPv4 somente ou como uma implementação de pilha dupla. Os pontos de extremidade que usam apenas IPv6 não podem usar nenhum desses recursos.
  
> [!NOTE]
> Em uma implantação com pilha dupla, mesmo que um cliente Skype for Business Server se conecte a um Skype for Business Server usando IPv6, o Skype for Business Server fará um melhor esforço para mapear um endereço IPv4 apropriado para dar suporte ao E9-1-1. 
  
Não há suporte para o serviço de Informações de Local com endereços IPv6.
  
Exchange Unificação de Mensagens (UM) não dá suporte a IPv6. Para Exchange UM, certifique-se de que a resolução DNS não retorna um endereço IPv6. O uso de IPv6 pode causar falha quando as chamadas são enviadas para a caixa postal. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Outro Skype for Business Server suporte a recursos para IPv6
<a name="Ent_V"> </a>

Além dos recursos e componentes mencionados anteriormente, o Skype for Business Server oferece suporte a IPv6 para os seguintes recursos:
  
- **Chat Persistente**
    
    Configure iPv6 para Chat Persistente usando o Construtor de Topologias. Para obter detalhes sobre como configurar o Chat Persistente, consulte a documentação Implantando o Servidor de Chat Persistente.
    
- **Relatórios de qualidade de experiência (QoE) e registro de detalhes de chamada (CDR)**
    
    Os relatórios de monitoramento incluem o endereço IP como ele é armazenado no banco de dados do Monitoring Server, seja do tipo IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisitos técnicos para IPv6
<a name="tech"> </a>

Se você planeja configurar o Skype for Business Server para IPv6, lembre-se dos seguintes requisitos:
  
- Para usar endereços IPv6 com Skype for Business Server, você precisa criar registros DNS (sistema de nomes de domínio) para registros que devem ser descobertos e resolvidos para um endereço IPv6. O DNS IPv6 usa um registros de host AAAA (quad-A). Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6. Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.
    
    É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.
    
- Cada endereço IPv6 possui um escopo. Os três escopos que você pode usar para endereçamento IPv6 são endereços globais IPv6 (semelhantes a endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhantes aos intervalos de endereçoS IPv4 privados) e endereços locais de link IPv6 (semelhantes a endereços IP privados automáticos no Windows Server para IPv4). Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo. 
    
> [!IMPORTANT]
> IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços atribuídos no nível do servidor Windows e no nível Skype for Business Server funcionem conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerações de migração e coexistência para IPv6
<a name="migration"> </a>

O IP versão 6 (IPv6) não é suportado no Lync Server 2010 ou Office Communications Server. Para fins de pilotagem, você pode testar o Lync Server 2010 e Skype for Business Server coexistência de pilha dupla. Recomendamos que todos os pools de um determinado site central sejam atualizados para Skype for Business Server antes de habilitar o IPv6 (rede de pilha dupla) para qualquer um dos pools. Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.
  
Os cenários a seguir são suportados durante a migração e coexistência:
  
- Skype for Business Server, pools do Lync Server 2013 e do Lync Server 2010 no modo IPv4, coexistindo com Skype for Business Server no modo de pilha dupla.
    
- Skype for Business Server pool no modo somente IPv6, se o pool somente IPv6 for silo.
    
## <a name="see-also"></a>Confira também
<a name="migration"> </a>

[Configurar tipos de endereço IP em Skype for Business](ip-address-types.md)

[Arquitetura de endereçamento ip versão 6](https://tools.ietf.org/html/rfc4291)
  
[Formato de endereço global unicast IPv6](https://tools.ietf.org/html/rfc3587)
  
[Endereços unicast IPv6 locais exclusivos](https://tools.ietf.org/html/rfc4193)
