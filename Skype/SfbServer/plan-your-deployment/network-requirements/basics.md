---
title: Noções básicas do DNS
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 tem softwares integrados que podem fornecer serviços DNS, portanto, talvez você queira revisar a documentação disponível, como o Guia de Cenário de Política DNS. Você pode escolher uma solução de terceiros, se preferir.
ms.openlocfilehash: 86d9973015acd389cdbdfdb252cb98b8a9a5cbee
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387649"
---
# <a name="dns-basics"></a>Noções básicas do DNS
 
Windows Server 2016 tem softwares integrados que podem fornecer serviços DNS, portanto, talvez você queira revisar a documentação disponível, como o Guia de Cenário de [Política DNS](/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Você pode escolher uma solução de terceiros, se preferir.
  
Recomendamos que, como prática prática, você dedique um servidor específico em sua implementação para fornecer DNS. Você poderia defini-lo em um dos servidores dedicados a uma das funções de servidor do Skype for Business, mas se esse servidor também fazia parte de um pool e foi desativado por acidente Skype for Business não funcionaria até que os serviços DNS fossem re-estabelecidos.
  
## <a name="dns-records"></a>Registros DNS

Cada mapeamento de um nome para um endereço IP (e que pode ser um endereço IPv4 ou IPv6) é armazenado em um registro DNS no servidor DNS. O nome é descrito no Relatório DNS especificamente como um FQDN — um Nome de Domínio Totalmente Qualificado. Embora  *contoso.com*  seja um nome de domínio válido, ele é shorthand *\*para .contoso.com*  , portanto, é ambíguo e possivelmente pode se referir a qualquer servidor no domínio. Um exemplo de FQDN que faria referência a um único servidor em seu domínio pode ser **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Por padrão, o nome do computador de um computador que não está ingressado em um domínio é um nome de host e não um FQDN (nome de domínio totalmente qualificado). O Construtor de Topologia usa FQDNs, não nomes de host. Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio. **Use somente caracteres** padrão (incluindo A-Z, a-z, 0-9 e hífens) ao atribuir FQDNs aos servidores que executam Skype for Business Server. Não use caracteres Unicode ou sublinhados. Os caracteres incompatíveis em um FQDN frequentemente não são suportados no DNS externo e CAs públicos (isto é, quando o FQDN deve ser atribuído ao SN no certificado).
  
Além de um endereço IP, o FQDN poderia mapear para um **VIP** — um endereço IP virtual. Um VIP é um endereço IP que não corresponde a uma interface de rede física real. Um VIP geralmente aponta para um pool de servidores que executam uma função de servidor ou para um par de servidores configurados para redundância e tolerância a falhas.
  
Há vários tipos de registro DNS, os mais relevantes para essa discussão são: 
  
- **R** — um registro de endereço ou registro host, retorna um endereço IPv4 de 32 bits. Mais comumente usado para mapear nomes de host para um endereço IP do host.
    
- **AAAA** — um registro de endereço IPv6. Retorna um endereço IPv6 de 128 bits. Mais comumente usado para mapear nomes de host para um endereço IP do host.
    
- **CNAME** — um registro de nome canônico. Isso resolve um nome para outro: a análise DNS repetirá a análise com o novo nome.
    
- **SRV** — um registro de serviço (registro SRV) especifica um serviço (um processo em um servidor) que é acessado em uma porta específica e uma combinação de IP. Os nomes dos serviços que exigem um registro de serviço são fixos e não podem ser personalizados além de fazê-los parte do seu domínio SIP. Alguns serviços de usuário usam URLs simples. Um registro SRV deve apontar para um local no mesmo domínio SIP, portanto, se você tiver vários domínios, precisará de vários registros SRV para um determinado serviço.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Como escolher um nome de domínio SIP
<a name="BK_NameSIP"> </a>

O nome de domínio SIP de uma organização geralmente se alinha com os endereços de email dados aos seus usuários. Se um usuário em sua organização tivesse um endereço de email como Brown@contoso.com, \<sip-domain\> a preferência para uma organização com o nome de domínio contoso.com é simplesmente contoso.com.
  
### <a name="multiple-sip-domains"></a>Vários domínios SIP

 Sua organização pode, em alguns casos, precisar de vários domínios SIP. Como exemplo, se Fabrikam.com foi adquirido pelo contoso.com, talvez seja necessário criar um novo domínio SIP do Skype for Business Server reconhece e aceitará a conexão. Ao fazer isso, você precisará criar um conjunto adicional de todos os registros DNS que usam contoso.com, com novos FQDNs que mostram onde enviar solicitações para Fabrikam.
  
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="BK_NameSIP"> </a>

Você pode usar o DNS para compartilhar a carga de tráfego entre vários servidores que estão definidos como um pool de servidores. Para fazer isso, você criaria vários registros A para o FQDN do pool, cada um deles aponta para o endereço IP de um nó no pool.
  
Consulte [Balanceamento de carga DNS para](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) discussões adicionais sobre balanceamento de carga.
