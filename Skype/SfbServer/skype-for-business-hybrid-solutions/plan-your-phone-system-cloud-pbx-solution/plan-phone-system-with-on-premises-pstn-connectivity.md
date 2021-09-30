---
title: Planejar Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Saiba mais sobre as considerações de planejamento para Sistema de Telefonia (Cloud PBX) com conectividade PSTN local.
ms.openlocfilehash: 074afcd05b62501784d5c37d10d698f6c29bdd78
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014305"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planejar Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server

> [!Important]
> Skype for Business Online será retirado em 31 de julho de 2021 após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba mais sobre as considerações de planejamento para Sistema de Telefonia (Cloud PBX) com conectividade PSTN local.

Esse conteúdo é relevante se você já tiver Skype for Business Server ou o Lync Server 2013 implantado no local. Para outros cenários, consulte [Soluções de telefonia da Microsoft.](/microsoftteams/cloud-voice-landing-page)

 Sistema de Telefonia com conectividade PSTN local permite que você aproveite os recursos Sistema de Telefonia (Cloud PBX) para seus usuários. Isso pode ajudar com os seguintes cenários:

- Você tem alguns dos seus Skype for Business usuários locais e outros em casa no Skype for Business Online. Agora você pode habilitar Sistema de Telefonia recursos e recursos para os usuários que estão no Skype for Business Online, mas continuar a usar a conectividade PSTN local.

- Você tem uma implantação local e deseja mover alguns ou todos os seus usuários para Skype for Business Online, mas continuar a usar a conectividade PSTN local.

    > [!IMPORTANT]
    > Para habilitar os usuários para Sistema de Telefonia com conectividade PSTN local, seu endereço SIP deve estar em seu próprio domínio. O uso do domínio padrão para Microsoft 365 ou Office 365, onmicrosoft.com, não é suportado. 

Para saber mais sobre Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamada [PSTN para](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)Skype for Business .

## <a name="feature-comparison"></a>Comparação de recursos

Cloud PBX com conectividade PSTN local não oferece o mesmo conjunto de recursos que uma solução de Enterprise Voice local. Para ajudá-lo a decidir se o Cloud PBX com conectividade PSTN local fornecerá o conjunto de recursos correto para sua organização, consulte Aqui está o que você obter com [Cloud PBX](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json).

## <a name="benefits-and-planning-considerations"></a>Benefícios e considerações de planejamento

> [!CAUTION]
> Os dispositivos do Lync Telefone Edition devem ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mudar para o Skype for Business Online.
Se você mover seus usuários do local para o online antes de atualizar o firmware, os usuários não poderão se conectar usando seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU REDEFINIR O TELEFONE COM FORÇA ANTES DE MOVER O USUÁRIO DE VOLTA PARA O AMBIENTE LOCAL.
Se uma redefinição de disco rígido for executada enquanto o dispositivo não estiver no firmware mínimo, o padrão será usar a Autenticação de PIN, que não é suportada no Skype for Business Online. Para obter mais informações, consulte [Getting phones for Skype for Business Online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Ao implantar o Sistema de Telefonia com conectividade PSTN local, você pode mover seus usuários para a nuvem por meio do Skype for Business Online em seu próprio ritmo, mantendo sua conectividade PSTN local. Se você tiver um PBX, continue a usá-lo para fornecer conectividade PSTN para os usuários que você move para a nuvem. Depois que um usuário for movido para o Skype for Business Online e Sistema de Telefonia, o telefone PBX herdado não funcionará mais, mas seu número de telefone será roteado para qualquer um dos clientes do Skype for Business para computadores ou telefones inteligentes, bem como para telefones de mesa compatíveis com Skype for Business. Depois de portados, Sistema de Telefonia usuários e usuários PBX herdados podem ligar uns para os outros normalmente, bem como fazer/receber chamadas PSTN usando seu número de telefone normal.

Você pode ter um recurso personalizado ou um complemento importante para seu PBX herdado, como um call center. Se o recurso personalizado não estiver disponível no Sistema de Telefonia, você deve deixar os usuários que exigem esse recurso personalizado no local com o PBX herdado e apenas porta os usuários que não precisam acessar o recurso personalizado para Sistema de Telefonia com conectividade PSTN local.

Para uma lista de PBXs herdados que interoperam diretamente com o Skype for Business Server 2015, consulte [Infrastructure Qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). Se o PBX não estiver nessa lista, você poderá usar um Controlador de Borda de Sessão para conectar seu PBX com Sistema de Telefonia no Skype for Business Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerações sobre a qualidade e o desempenho da rede

Ao implantar um serviço hospedado na nuvem como Sistema de Telefonia com conectividade PSTN local, você deve ter o seguinte em mente. Em uma implantação Skype for Business Server 2015 Enterprise Voice 2015, toda a infraestrutura e os clientes estão na própria rede da empresa. A qualidade e o desempenho dessa rede, que é fundamental para áudio e vídeo de alta qualidade, estão sob o controle direto da equipe corporativa. Com Sistema de Telefonia com conectividade PSTN local, há três redes envolvidas, duas das quais o cliente é responsável, mas apenas uma das quais a equipe corporativa tem controle direto sobre:

- **Rede global de entrega de mídia da Microsoft** Infraestrutura e rede global de nuvem da Microsoft. Sistema de Telefonia servidores e tráfego percorrem essa rede.

- **Enterprise/Cloud PSTN Interconnect** Essa é a rede que conecta sua empresa à nuvem. Isso não é necessariamente o mesmo que sua conexão genérica com a Internet.

- **Rede própria da sua empresa** A qualidade da mídia em tempo real depende muito da sua própria rede: especialmente da rede WiFi e da qualidade da interconexão usada para alcançar a nuvem.

> [!NOTE]
> Para obter mais informações sobre como ajustar o desempenho no Skype for Business Online, consulte [Tune Skype for Business Online performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Pré-requisitos para usar Sistema de Telefonia com conectividade PSTN local

Antes de configurar o Sistema de Telefonia com conectividade PSTN local e mover os usuários para o Skype for Business Online, você deve confirmar se tem os seguintes pré-requisitos no local:

 **Versões do servidor local.** As versões dos servidores em sua implantação local devem estar listadas na tabela a seguir para dar suporte Sistema de Telefonia com conectividade PSTN local.


| **Função de servidor**                                       | **Versões com suporte\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borda de Federação\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Pool Interno da Rota de Federação de Próximo Salto  <br/> | Skype for Business Server 2015, Atualização Cumulativa 6.0.9319.235 de março de 2016 ou superior (Front-End ou Director)  <br/> |
| Servidor de Usuário Front-End  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor de Borda  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Mediação  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*As versões mínimas com suporte são:

- Skype for Business Server 2015, Atualização Cumulativa 6.0.9319.235 de março de 2016

- Atualização Cumulativa 5.0.8308.920 do Lync Server 2013 de julho de 2015

\*\*A rota de federação para todos os domínios SIP suportados deve ser roteada pelo servidor de borda Skype for Business Server 2015 executando a Atualização Cumulativa de março de 2016 ou superior. Se o pool de usuários estiver no Lync Server 2013, esse tráfego de pool externo permanecerá no Servidor de Borda do Lync Server 2013. 

Além disso, você deve garantir o seguinte:

- **A Enterprise Voice local é configurada e testada para usuários locais** Isso inclui componentes de conectividade PSTN. Para obter mais informações, consulte os tópicos a seguir se você estiver usando o Skype for Business Server 2015, consulte [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) and Deploy Enterprise Voice in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se você estiver usando o Lync Server 2013, consulte [Planning for Enterprise Voice in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) and [Deploying Enterprise Voice in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice).

- **Sincronização do Active Directory** Você deve configurar a sincronização do Active Directory usando o Azure AD Conexão. Para obter mais informações, consulte [Azure AD Conexão](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom).

    > [!NOTE]
    > A versão do AAD Conexão que você usa deve ser a versão 1.0.9125.0 ou posterior. Se você estiver usando uma versão anterior do AAD Conexão ferramentas ou DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter todas as regras personalizadas definidas em seu ambiente. 

- **Configurar sua implantação híbrida** Se todos os usuários do seu Skype for Business estão atualmente no local ou online ou se você tem uma combinação no momento, você deve concluir as etapas para configurar uma implantação híbrida do Skype for Business Server ou do Lync Server 2013, conforme descrito em [Deploy hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). Para obter mais informações sobre implantações híbridas, consulte [Plan hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). 

    Se você estiver usando o Lync Server 2013, consulte [Lync Server 2013 hybrid](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid).

- **(Recomendado) Serviços de Federação do Active Directory (AD FS).** Recomendamos a implantação do AD FS para dar suporte ao Login Único. Para obter mais informações, consulte [Serviços de Federação do Active Directory (AD FS)](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10)).

Para obter informações sobre como implantar Sistema de Telefonia, consulte [Enable users for Sistema de Telefonia with on-premises PSTN connectivity in Skype for Business Server](enable-users-for-phone-system.md).
