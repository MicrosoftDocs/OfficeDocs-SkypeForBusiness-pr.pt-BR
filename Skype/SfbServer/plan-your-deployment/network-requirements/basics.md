---
title: Noções básicas DNS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tem o software interno que pode fornecer serviços DNS, portanto, talvez você queira revisar a documentação disponível, como o guia de cenário de política de DNS. Se você preferir, você pode escolher uma solução de terceiros.
ms.openlocfilehash: df6a693c50b3ca8b61baf0e47e0d019478f3cbf9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="dns-basics"></a>Noções básicas DNS
 
Windows Server 2016 tem o software interno que pode fornecer serviços DNS, portanto, talvez você queira revisar a documentação disponível, como o [Guia de cenário de política de DNS](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Se você preferir, você pode escolher uma solução de terceiros.
  
Recomendamos que como uma prática recomendada você dedique um servidor específico na sua implementação para fornecer o DNS. Você poderia potencialmente montá-lo em um dos servidores dedicados a uma do Skype para funções de servidor de negócios, mas se esse servidor também fazia parte de um pool e receber descomissionar por acidente Skype para negócios seriam mau funcionamento até que os serviços DNS foram restabelecidos.
  
## <a name="dns-records"></a>Registros DNS

Cada mapeamento de um nome para um endereço IP (e que poderia ser um endereço IPv4 ou IPv6) é armazenado em um registro DNS no servidor DNS. O nome é descrito no relatório de DNS especificamente como um FQDN — um nome de domínio totalmente qualificado. Embora *contoso.com* é um nome de domínio válidos, é forma abreviada de * \*. contoso.com* , portanto, ela é ambígua e, possivelmente, poderia se referir a qualquer servidor no domínio. Um exemplo de um FQDN que pode se referir a um único servidor em seu domínio pode ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Por padrão, o nome de um computador que não ingressou em um domínio é um nome de host, não um FQDN (nome de domínio totalmente qualificado). FQDNs, nomes de host não usa o construtor de topologias. Portanto, você deve configurar um sufixo DNS no nome do computador a ser implantado como um servidor de borda que não ingressou em um domínio. **Use somente caracteres padrão** (incluindo A-Z, a-z, 0-9 e hifens) ao atribuir FQDNs para os servidores que executam o Skype para Business Server. Não use caracteres Unicode nem sublinhados. Caracteres não padrão em um FQDN, em geral, não recebem suporte de DNSs externos e CAs públicas (ou seja, quando for necessário atribuir o FQDN ao nome da entidade no certificado).
  
Além de um endereço IP, o FQDN pode mapear para um **VIP** — um endereço IP virtual. Um VIP é um endereço IP que não corresponde a uma interface de rede física real. Geralmente, um VIP aponta para um pool de servidores executando uma função de servidor, ou para um par de servidores configurados para redundância e tolerância a falhas.
  
Há vários tipos de registro DNS, aqueles que são mais relevantes para essa discussão são: 
  
- **Uma** — um registro de endereço ou um registro de Host, retorna um endereço IPv4 de 32 bits. Mais comumente usadas para mapear nomes de host para um endereço IP do host.
    
- **AAAA** — um registro de endereço IPv6. Retorna um endereço IPv6 de 128 bits. Mais comumente usadas para mapear nomes de host para um endereço IP do host.
    
- **CNAME** — um registro de nome canônico. Um nome é resolvido para outro: a pesquisa de DNS repetirá a pesquisa com o novo nome.
    
- **SRV** — um registro de serviço (SRV registro) especifica um serviço (um processo em um servidor) que é acessado em uma porta específica e a combinação de IP. Os nomes dos serviços que exigem um registro de serviço estão corrigidos e não podem ser personalizados, além de torná-los parte do seu domínio SIP. Alguns serviços de usuário usem URLs simples. Um registro SRV deve apontar para um local no mesmo domínio SIP, portanto, se você tiver vários domínios você precisará vários registros SRV de um serviço específico.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Como escolher um nome de domínio SIP
<a name="BK_NameSIP"> </a>

Geralmente, o nome de domínio SIP da organização se alinha com os endereços de email fornecidos aos seus usuários. Se um usuário em sua organização teria um endereço de email como Brown@contoso.com, o preferencial \<domínio sip\> para uma organização com o domínio contoso.com nome é simplesmente contoso.com.
  
### <a name="multiple-sip-domains"></a>Vários domínios SIP

 Em alguns casos, o sua organização talvez seja necessário vários domínios SIP. Por exemplo, se Fabrikam.com tiver sido adquirido por contoso.com, convém criar um novo domínio SIP que Skype para Business Server reconhece e aceitará a conexão de. Quando você fizer isso, você precisa criar um conjunto adicional de todos os registros DNS que usam contoso.com, com os FQDNs novos que mostram para onde enviar solicitações para Fabrikam.
  
## <a name="dns-load-balancing"></a>Balanceamento de carga do DNS
<a name="BK_NameSIP"> </a>

Você pode usar o DNS para compartilhar carga de tráfego entre vários servidores que estão configurados como um pool de servidores. Para fazer isso, você deve criar vários registros para o FQDN do pool, cada um deles aponta para o endereço IP de um nó do pool.
  
Consulte o [balanceamento de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) para discussões adicionais de balanceamento de carga.
  

