---
title: Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Saiba mais sobre as considerações de planejamento para o sistema telefônico no Office 365 (Cloud PBX) com conectividade PSTN local.
ms.openlocfilehash: a134b4dbe48d302ee8be8df528e6bbebac336b8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814479"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server

Saiba mais sobre as considerações de planejamento para o sistema telefônico no Office 365 (Cloud PBX) com conectividade PSTN local.

Esse conteúdo é relevante se você já tiver o Skype for Business Server ou o Lync Server 2013 implantado no local. Para outros cenários, consulte [soluções de telefonia da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 O sistema telefônico no Office 365 com conectividade PSTN local permite que você aproveite os recursos do sistema de telefonia (Cloud PBX) para seus usuários. Isso pode ajudar nos seguintes cenários:

- Você tem alguns dos seus usuários do Skype for Business hospedados no local e outras pessoas em casa no Skype for Business online. Agora você pode habilitar o sistema telefônico em recursos do Office 365 e recursos para seus usuários hospedados no Skype for Business Online, mas continuar a usar a conectividade PSTN local.

- Você tem uma implantação local e deseja mover alguns ou todos os seus usuários para o Skype for Business Online, mas continuar a usar a conectividade PSTN local.

    > [!IMPORTANT]
    > Para habilitar com êxito os usuários para o sistema telefônico no Office 365 com conectividade PSTN local, o endereço SIP dele deve estar em seu próprio domínio. Não há suporte para o uso do domínio padrão para o Office 365 onmicrosoft.com. 

Para saber mais sobre o sistema telefônico no Office 365, incluindo licenciamento e planos, consulte [planos de chamada PSTN para o Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparação de recursos

O Cloud PBX com conectividade PSTN local não oferece o mesmo conjunto de recursos que uma solução de Enterprise Voice local totalmente local. Para ajudá-lo a decidir se o Cloud PBX com conectividade PSTN local fornecerá o conjunto de recursos correto para sua organização, veja [aqui o que você obtém com o Cloud PBX](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Benefícios e considerações de planejamento

> [!CAUTION]
> Os dispositivos Lync Phone Edition DEVEM ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mover para o Skype for Business Online.
Se você mover seus usuários da implantação local para a online antes de atualizar o firmware, eles não conseguirão se conectar usando os seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU FAZER A REINICIALIZAÇÃO FORÇADA DO TELEFONE ANTES DE MOVER O USUÁRIO DE VOLTA PARA SEU AMBIENTE LOCAL.
Se houver uma reinicialização forçada enquanto o dispositivo não estiver no firmware mínimo, o padrão será definido como Autenticação PIN, que não tem suporte no Skype for Business Online. Para obter mais informações, consulte como [obter telefones para o Skype for Business online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Ao implantar o sistema telefônico no Office 365 com conectividade PSTN local, você pode mover seus usuários para a nuvem via Skype for Business online em seu próprio ritmo, mantendo a conectividade PSTN local. Se você tiver um PBX, continuará utilizando-o para fornecer conectividade PSTN aos usuários transferidos para a nuvem. Depois que um usuário for movido para o Skype for Business Online e para o sistema telefônico no Office 365, o seu telefone PBX herdado deixará de funcionar, mas o número de telefone do Skype for Business para PCs ou telefones fixos, bem como telefone de mesa compatível com o Skype for Business meses. Uma vez portado, o sistema telefônico nos usuários do Office 365 e do PBX herdado podem ligar para cada um dos outros normalmente e fazer/receber chamadas PSTN usando o número de telefone normal.

Você pode ter um recurso personalizado ou um complemento de maior porte para seu PBX herdado, como um call center. Se o recurso personalizado não estiver disponível no momento no sistema telefônico no Office 365, você deverá deixar esses usuários que exijam o recurso personalizado no local do PBX herdado e simplesmente portar os usuários que não precisam acessar o recurso personalizado para o sistema telefônico no Office 365 com conectividade PSTN local.

Para obter uma lista de PBXs herdadas que interagem diretamente com o Skype for Business Server 2015, consulte [infraestrutura qualificada para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se o seu PBX não estiver nesta lista, você pode usar um controlador de borda de sessão para conectar seu PBX com o sistema telefônico no Office 365 no Skype for Business online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerações de rede para qualidade e desempenho

Ao implantar um serviço hospedado na nuvem como o sistema telefônico no Office 365 com conectividade PSTN local, você deve ter em mente o seguinte. Em uma implantação unificada do Skype for Business Server 2015 Enterprise Voice, todos os clientes e infraestruturas estão na própria rede da empresa. A qualidade e o desempenho dessa rede, fundamentais para que se tenha áudio e vídeo de alta qualidade, estão sob o controle direto da equipe da empresa. Com o sistema telefônico no Office 365 com conectividade PSTN local, há três redes envolvidas, duas das quais o cliente é responsável, mas somente uma delas tem o controle direto de:

- **Rede de entrega de mídia global da Microsoft** Rede e infraestrutura de nuvem global da Microsoft. O Office 365 e o sistema telefônico no Office 365 servidores e tráfego atravessam esta rede.

- **Interconexão PSTN empresarial/nuvem** Esta é a rede que conecta sua empresa à nuvem do Office 365. Isso não é necessariamente o mesmo que sua conexão genérica com a Internet.

- **Rede da sua empresa** A qualidade da mídia em tempo real depende muito da sua própria rede: especialmente da rede WiFi e da qualidade da interconexão usada para alcançar a nuvem do Office 365.

> [!NOTE]
> Para obter mais informações sobre como ajustar o desempenho no Skype for Business Online, consulte [ajustar o desempenho do Skype for Business online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Pré-requisitos para usar o sistema telefônico no Office 365 com conectividade PSTN local

Antes de poder configurar o sistema telefônico no Office 365 com conectividade PSTN local e mover usuários para o Skype for Business Online, você deve confirmar que tem os seguintes pré-requisitos em vigor:

 **Versões do servidor local.** As versões dos servidores em sua implantação local devem estar listadas na tabela a seguir para dar suporte ao sistema telefônico no Office 365 com conectividade PSTN local.


| **Função de servidor**                                       | **Versões com suporte\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borda da Federação\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de pool interno de rota de federação de próximo salto  <br/> | Skype for Business Server 2015, atualização cumulativa 6.0.9319.235 ou posterior (tront end ou diretor) de março de 2016   <br/> |
| Servidor de usuário Front-End  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor de Borda  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Mediação  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*As versões mínimas compatíveis são:

- Skype for Business Server 2015, atualização cumulativa 6.0.9319.235 de março de 2016 

- Lync Server 2013, atualização cumulativa 5.0.8308.920 de julho de 2015

\*\*A rota de Federação para todos os domínios SIP com suporte deve direcionar o servidor de borda do Skype for Business Server 2015 executando a atualização cumulativa 2016 de março ou mais recente. Se o pool de usuários estiver no Lync Server 2013, esse tráfego de pool externo permanecerá no Servidor de Borda do Lync Server 2013. 

Além disso, você deve garantir o seguinte:

- **A Enterprise Voice local é configurada e testada para usuários locais** Isso inclui componentes de conectividade PSTN. Para obter mais informações, consulte os tópicos a seguir se você estiver usando o Skype for Business Server 2015, consulte [planejar o Enterprise Voice no Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [implantar o Enterprise Voice no Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se você estiver usando o Lync Server 2013, consulte [planejando o Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [implantando o Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronização do Active Directory** Você deve configurar a sincronização do Active Directory usando o Azure AD Connect. Para obter mais informações, consulte [Gerenciando o Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Você deve usar a versão 1.0.9125.0 ou posterior do AAD Connect. Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou do DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter qualquer regra personalizada que você tenha definido em seu ambiente. 

- **Configurar sua implantação híbrida** Se todos os seus usuários do Skype for Business estão hospedados online ou no local, ou se você tem uma combinação no momento, deve completar as etapas para configurar uma implantação híbrida do Skype for Business Server ou do Lync Server 2013, conforme descrito em [implantar conectividade híbrida entre o Skype for Business Server e o Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para obter mais informações detalhadas sobre implantações híbridas, consulte [planejar conectividade híbrida entre o Skype for Business Server e o Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Se você estiver usando o Lync Server 2013, consulte [Lync server 2013 Hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Usar Serviços de Federação do Active Directory (AD FS).** Recomendamos implantar o AD FS para dar suporte a Logon Único. Para obter mais informações, consulte [serviços de Federação do Active Directory (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Para obter informações sobre a implantação do sistema telefônico no Office 365, consulte [habilitar usuários do sistema telefônico no office 365 com conectividade PSTN local no Skype for Business Server](enable-users-for-phone-system.md).


