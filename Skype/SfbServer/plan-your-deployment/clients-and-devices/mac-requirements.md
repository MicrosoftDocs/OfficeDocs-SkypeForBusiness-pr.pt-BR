---
title: Skype for Business nos requisitos do cliente Mac
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013454"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business nos requisitos do cliente Mac
 
Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
  
O [cliente do Skype for Business no Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponível para download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware e software para o Skype for Business no Mac

O cliente do Skype for Business no Mac requer o Mac OS X El Capitan e superior e usa pelo menos 100 MB de espaço em disco. Oferecemos suporte para o uso de todos os dispositivos de áudio e vídeo integrados. Dispositivos externos devem estar no [Catálogo de soluções do Skype for Business](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Esta lista é preliminar e alguns dispositivos podem estar qualificados para o Lync, mas não têm suporte no Skype for Business no Mac. Consulte os [requisitos do sistema](https://products.office.com/office-system-requirements) para obter o mínimo necessário de hardware.
  
### <a name="legacy-mac-clients"></a>Clientes Mac herdados

O Skype for Business Server 2015 também suporta os seguintes clientes herdados em computadores que executam o Mac OS 10.5.8 ou o Service Pack ou versão mais recente (baseado em Intel) sistemas operacionais (o sistema operacional Mac OS 10,9 não tem suporte no momento). Para obter detalhes sobre os recursos suportados, consulte [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte [Lync para mac 2011 guia de implantação](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (consulte o [Guia de implantação do Communicator for mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Esses clientes não são compatíveis com o Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestrutura para o Skype for Business no Mac
<a name="Infrastructure"> </a>

O cliente do Skype for Business no Mac aproveita a plataforma de gerenciamento de comunicações unificadas (UCMP), bem como a API da Web de comunicações unificadas (UCWA) que nossos clientes de mobilidade usam.
  
O cliente tem os mesmos requisitos que nossos clientes de mobilidade em que você deve ter um servidor de borda de acesso e proxy reverso implantados em uma configuração com suporte. 
  
### <a name="authentication"></a>Autenticação

O Skype for Business no cliente Mac oferece suporte à autenticação baseada em certificado, à autenticação moderna da Microsoft e à autenticação multifator quando implantado e habilitado.
  
> [!NOTE]
> Devido a uma limitação atual, as credenciais do Exchange do usuário devem ser as mesmas que suas credenciais do Skype for Business. 
  
### <a name="certificates"></a>Certificados

Certificados em uso na borda de acesso, o proxy reverso e os servidores front-end não devem usar o algoritmo de hash SHA-512.
  
A lista de revogação de certificado HTTP deve ser definida e acessível pelo cliente. Por exemplo, não há suporte para uma entrada LDAP no certificado como sua lista de revogação de certificado.
  
### <a name="dns"></a>DNS

A mobilidade deve ser implantada corretamente para que o Skype for Business no cliente Mac funcione corretamente. Um cenário de falha comum é ter as duas entradas DNS a seguir resolvidas na rede interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obter mais informações, consulte: [implantando mobilidade no Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e o [Guia de mobilidade do Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Confira também
<a name="Infrastructure"> </a>

[Requisitos de DNS para o Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Perguntas Frequentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conhecidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)
