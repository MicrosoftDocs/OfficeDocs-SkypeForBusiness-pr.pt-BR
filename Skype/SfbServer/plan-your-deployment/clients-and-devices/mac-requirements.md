---
title: Requisitos do cliente Skype for Business no Mac
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
ms.openlocfilehash: aca2329fa3e7d42dfd1aaf47e4c069773c7206f0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221713"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisitos do cliente Skype for Business no Mac
 
Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
  
O [cliente Skype for Business no Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) está disponível para download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware e software para o Skype for Business no Mac

O cliente Skype for Business no Mac exige o Mac OS X El Capitan e versões mais recentes e usa pelo menos 100 MB de espaço em disco. Oferecemos suporte para o uso de dispositivos de áudio e vídeo totalmente integrados. Dispositivos externos devem estar no [Catálogo de soluções do Skype for Business](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Esta lista é preliminar e alguns dispositivos podem estar qualificados para o Lync, mas não são compatíveis com o Skype for Business no Mac. Consulte os [requisitos do sistema](https://products.office.com/en-us/office-system-requirements) para o mínimo necessário de hardware.
  
### <a name="legacy-mac-clients"></a>Clientes Mac herdados

O Skype for Business Server 2015 também é compatível com os seguintes clientes herdados em computadores que executam o Mac OS 10.5.8 ou versões mais recentes de Service Pack ou lançamento (baseados em Intel) (o sistema operacional Mac OS 10,9 não tem suporte no momento). Para obter detalhes sobre os recursos com suporte, consulte [comparação de recursos do cliente de área de trabalho para o Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte [Guia de implantação do Lync para mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (consulte [Guia de implantação do Communicator para mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Esses clientes não são compatíveis com o Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestrutura para o Skype for Business no Mac
<a name="Infrastructure"> </a>

O cliente Skype for Business no Mac aproveita a plataforma de gerenciamento unificado de comunicações (UCMP), bem como a API da Web de comunicação unificada (UCWA) que os nossos clientes de mobilidade usam.
  
O cliente tem os mesmos requisitos que nossos clientes de mobilidade, de que você deve ter um Servidor de Borda de Acesso e um Proxy Reverso implantados em uma configuração compatível. 
  
### <a name="authentication"></a>Autenticação

O cliente Skype for Business no Mac tem suporte para autenticação baseada em certificados, autenticação moderna da Microsoft e autenticação multifator quando implantada e habilitada.
  
> [!NOTE]
> Devido a uma limitação atual, as credenciais do usuário do Exchange devem ser iguais às credenciais do Skype for Business. 
  
### <a name="certificates"></a>Certificados

Os certificados usados nos servidores de Borda de Acesso, Proxy Reverso e Front-End não podem usar o algoritmo de hash SHA-512.
  
A Lista de Revogação de Certificados HTTP deve ser definida e acessível pelo cliente. Por exemplo, não oferecemos suporte a uma entrada LDAP no certificado como sua lista de revogação de certificado.
  
### <a name="dns"></a>DNS

A mobilidade deve ser implantada corretamente para que o Skype for Business no cliente Mac funcione corretamente. Uma situação de falha comum é ter as duas entradas DNS a seguir capazes de resolver na rede interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obter mais informações, consulte: implantando a [mobilidade no Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e o [Guia de mobilidade do Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Confira também
<a name="Infrastructure"> </a>

[Requisitos de DNS para o Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Perguntas frequentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conhecidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)
