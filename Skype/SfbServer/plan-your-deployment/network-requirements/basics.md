---
title: Noções básicas de DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: O Windows Server 2016 tem um software interno que pode fornecer serviços DNS, portanto, talvez você queira analisar a documentação disponível, como o guia de cenário de política de DNS. Você pode escolher uma solução de terceiros, se preferir.
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297271"
---
# <a name="dns-basics"></a>Noções básicas de DNS
 
O Windows Server 2016 tem um software interno que pode fornecer serviços DNS, portanto, talvez você queira analisar a documentação disponível, como o [Guia de cenário de política de DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Você pode escolher uma solução de terceiros, se preferir.
  
Recomendamos que, como prática recomendada, você dedicar um servidor específico em sua implementação para fornecer DNS. Você poderia configurá-lo em um dos servidores dedicados a uma das funções do servidor do Skype for Business, mas se esse servidor também estivesse fazendo parte de um pool e se tivesse sido descomissionado por acidente, o Skype for Business não funcionaria até que os serviços DNS fossem restabelecidos.
  
## <a name="dns-records"></a>Registros de DNS

Cada mapeamento de um nome para um endereço IP (e que pode ser um endereço IPv4 ou IPv6) é armazenado em um registro DNS no servidor DNS. O nome é descrito no relatório DNS especificamente como um FQDN, um nome de domínio totalmente qualificado. Embora *contoso.com* seja um nome de domínio válido, ele é abreviado para * \*. contoso.com* , portanto, é ambíguo e possivelmente se referir a qualquer servidor no domínio. Um exemplo de um FQDN que faz referência a um único servidor no seu domínio pode ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Por padrão, o nome do computador de um computador que não está associado a um domínio é um nome de host e não um FQDN (nome de domínio totalmente qualificado). O construtor de topologias usa FQDNs, não nomes de host. Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio. **Usar apenas caracteres padrão** (incluindo A-Z, a-z, 0-9 e hifens) ao atribuir FQDNs a seus servidores que executam o Skype for Business Server. Não use caracteres Unicode ou sublinhados. Normalmente, caracteres não padrão no FQDN não são suportados por DNS externo e CAs públicas (ou seja, quando o FQDN deve ser atribuído ao SN no certificado).
  
Além de um endereço IP, o FQDN pode mapear para um **VIP** — um endereço IP virtual. Um VIP é um endereço IP que não corresponde a uma interface de rede física real. Um VIP geralmente aponta para um pool de servidores executando uma função de servidor ou para um par de servidores configurados para redundância e tolerância a falhas.
  
Há vários tipos de registros DNS, aqueles que são mais relevantes para esta discussão são: 
  
- **A** — um registro de endereço ou um registro de host, retorna um endereço IPv4 de 32 bits. Comumente usado para mapear nomes de host para um endereço IP do host.
    
- **Aaaa** — um registro de endereço IPv6. Retorna um endereço IPv6 de 128 bits. Comumente usado para mapear nomes de host para um endereço IP do host.
    
- **CNAME** — um registro de nome canônico. Isso resolve um nome para outro: a pesquisa de DNS tentará novamente a pesquisa com o novo nome.
    
- **SRV** — um registro de serviço (registro SRV) especifica um serviço (um processo em um servidor) que é acessado em uma combinação específica de portabilidade e IP. Os nomes de serviços que exigem um registro de serviço são corrigidos e não podem ser personalizados além de fazerem parte do seu domínio SIP. Alguns serviços de usuário usam URLs simples. Um registro SRV deve apontar para um local no mesmo domínio SIP, portanto, se você tiver vários domínios, precisará de vários registros SRV para um serviço específico.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Como escolher um nome de domínio SIP
<a name="BK_NameSIP"> </a>

O nome de domínio SIP da organização geralmente se alinha com os endereços de email fornecidos a seus usuários. Se um usuário de sua organização tiver um endereço de email como Brown@contoso.com, o \<SIP SIP-Domain\> para uma organização com o nome de domínio contoso.com será simplesmente contoso.com.
  
### <a name="multiple-sip-domains"></a>Vários domínios SIP

 Sua organização pode, em alguns casos, precisar de vários domínios SIP. Como exemplo, se o Fabrikam.com foi adquirido pelo contoso.com, talvez seja necessário criar um novo domínio SIP para o qual o Skype for Business Server reconhece e aceitar a conexão. Ao fazer isso, você precisará criar um conjunto adicional de todos os registros DNS que usam contoso.com, com novos FQDNs que mostram para onde enviar solicitações para a Fabrikam.
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

Você pode usar o DNS para compartilhar a carga de tráfego entre vários servidores que estão configurados como um pool de servidores. Para fazer isso, você criaria vários registros a para o FQDN do pool, cada um apontando para o endereço IP de um nó no pool.
  
Consulte [balanceamento de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) para discussões adicionais de balanceamento de carga.
  

