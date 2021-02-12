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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Saiba mais sobre as considerações de planejamento para o Sistema de Telefonia (Cloud PBX) com conectividade PSTN local.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358807"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planejar Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server

> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Saiba mais sobre as considerações de planejamento para o Sistema de Telefonia (Cloud PBX) com conectividade PSTN local.

Esse conteúdo será relevante se você já tiver implantado o Skype for Business Server ou o Lync Server 2013 local. Para outros cenários, consulte [soluções de telefonia da Microsoft.](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

 O Sistema de Telefonia com conectividade PSTN local permite que você aproveite os recursos do Sistema de Telefonia (Cloud PBX) para seus usuários. Isso pode ajudar nos seguintes cenários:

- Alguns de seus usuários do Skype for Business estão no local e outros estão no Skype for Business Online. Agora você pode habilitar recursos e recursos do Sistema de Telefonia para seus usuários no Skype for Business Online, mas continuar a usar a conectividade PSTN local.

- Você tem uma implantação local e deseja mover alguns ou todos os usuários para o Skype for Business Online, mas continuar a usar a conectividade PSTN local.

    > [!IMPORTANT]
    > Para habilitar com êxito os usuários para o Sistema de Telefonia com conectividade PSTN local, seu endereço SIP deve estar em seu próprio domínio. O uso do domínio padrão para o Microsoft 365 ou Office 365, onmicrosoft.com, não é suportado. 

Para saber mais sobre o Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamada [PSTN para o Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>Comparação de recursos

O Cloud PBX com Conectividade PSTN local não oferece o mesmo conjunto de recursos que uma solução enterprise voice totalmente local. Para ajudá-lo a decidir se o Cloud PBX com conectividade PSTN local fornecerá o recurso certo para sua organização, consulte Aqui está o que você obter com o [Cloud PBX.](https://go.microsoft.com/fwlink/?LinkId=715517)

## <a name="benefits-and-planning-considerations"></a>Benefícios e considerações de planejamento

> [!CAUTION]
> Os dispositivos Lync Phone Edition DEVEM ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mudar para o Skype for Business Online.
Se você mover seus usuários do local para o online antes de atualizar o firmware, os usuários não poderão se conectar usando seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU REDEFINIR O TELEFONE ANTES DE MOVER O USUÁRIO DE VOLTA PARA SEU AMBIENTE LOCAL.
Se uma redefinição de disco rígido for executada enquanto o dispositivo não estiver no firmware mínimo, o padrão será usar a Autenticação PIN, que não é suportada no Skype for Business Online. Para saber mais, confira Obter [telefones para o Skype for Business Online.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

Ao implantar o Sistema de Telefonia com conectividade PSTN local, você pode mover seus usuários para a nuvem por meio do Skype for Business Online em seu próprio ritmo, mantendo sua conectividade PSTN local. Se você tiver um PBX, continuará a usá-lo para fornecer conectividade PSTN para os usuários que você move para a nuvem. Depois que um usuário for movido para o Skype for Business Online e o Sistema de Telefonia, o telefone PBX herdado não funcionará mais, mas o número de telefone será roteado para qualquer um dos clientes do Skype for Business para computadores ou smartphones, bem como para telefones de mesa compatíveis com o Skype for Business. Depois de portados, os usuários do Sistema de Telefonia e os usuários pbx herdados podem ligar uns para os outros normalmente, bem como fazer/receber chamadas PSTN usando seu número de telefone normal.

Você pode ter um recurso personalizado ou um complemento importante para seu PBX herdado, como um call center. Se o recurso personalizado não estiver disponível no momento no Sistema de Telefonia, você deverá deixar os usuários que exigem esse recurso personalizado localmente com o PBX herdado e porá-los apenas para os usuários que não precisam acessar o recurso personalizado para o Sistema de Telefonia com conectividade PSTN local.

Para uma lista de PBXs herdados que interoperam diretamente com o Skype for Business Server 2015, consulte Infraestrutura Qualificada  [para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Se seu PBX não estiver nessa lista, você poderá usar um Controlador de Borda de Sessão para conectar seu PBX ao Sistema de Telefonia no Skype for Business Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considerações de rede para qualidade e desempenho

Ao implantar um serviço hospedado na nuvem, como o Sistema de Telefonia com conectividade PSTN local, você deve ter o seguinte em mente. Em uma implantação puramente local do Skype for Business Server 2015 Enterprise Voice, toda a infraestrutura e os clientes estão na própria rede da empresa. A qualidade e o desempenho dessa rede, que são fundamentais para áudio e vídeo de alta qualidade, estão sob o controle direto da equipe da empresa. Com o Sistema de Telefonia com conectividade PSTN local, há três redes envolvidas, duas das quais o cliente é responsável, mas apenas uma das quais a equipe corporativa tem controle direto sobre:

- **Rede global de entrega de mídia da Microsoft** Infraestrutura e rede global de nuvem da Microsoft. Os servidores e o tráfego do Sistema de Telefonia atravessam essa rede.

- **Interconexão PSTN empresarial/nuvem** Essa é a rede que conecta sua empresa à nuvem. Isso não é necessariamente o mesmo que sua conexão genérica com a Internet.

- **Rede própria da sua empresa** A qualidade da mídia em tempo real depende muito da sua própria rede: especialmente da rede WiFi e da qualidade da interconexão usada para alcançar a nuvem.

> [!NOTE]
> Para obter mais informações sobre como ajustar o desempenho no Skype for Business Online, consulte [Ajustar o desempenho do Skype for Business Online.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Pré-requisitos para usar o Sistema de Telefonia com conectividade PSTN local

Antes de configurar o Sistema de Telefonia com conectividade PSTN local e mover os usuários para o Skype for Business Online, você deve confirmar se tem os seguintes pré-requisitos no local:

 **Versões do servidor local.** As versões dos servidores em sua implantação local devem estar listadas na tabela a seguir para dar suporte ao Sistema de Telefonia com conectividade PSTN local.


| **Função de servidor**                                       | **Versões com suporte\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borda de Federação\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Servidor do Pool Interno da Rota de Federação de Próximo Salto  <br/> | Skype for Business Server 2015, Atualização Cumulativa 6.0.9319.235 ou superior de março de 2016 (Front End ou Diretor)  <br/> |
| Servidor de usuário front-end  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor de Borda  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Servidor de Mediação  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*As versões mínimas com suporte são:

- Skype for Business Server 2015, atualização cumulativa 6.0.9319.235 de março de 2016

- Lync Server 2013 Atualização cumulativa 5.0.8308.920 de julho de 2015

\*\*A rota de federação para todos os domínios SIP com suporte deve ser roteada pelo Servidor de Borda do Skype for Business Server 2015 executando a Atualização Cumulativa de março de 2016 ou superior. Se o pool de usuários estiver no Lync Server 2013, esse tráfego de pool externo permanecerá no Servidor de Borda do Lync Server 2013. 

Além disso, você deve garantir o seguinte:

- **O Enterprise Voice local é configurado e testado para usuários locais** Isso inclui componentes de conectividade PSTN. For more information, see the following topics if you are using Skype for Business Server 2015, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Se você estiver usando o Lync Server 2013, consulte [Planning for Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e Implantando o Enterprise Voice no [Lync Server 2013.](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx)

- **Sincronização do Active Directory** Você deve configurar a sincronização do Active Directory usando o Azure AD Connect. Para obter mais informações, consulte [Gerenciando o Azure AD Connect.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > A versão do AAD Connect usada deve ser a versão 1.0.9125.0 ou posterior. Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter todas as regras personalizadas definidas em seu ambiente. 

- **Configurar sua implantação híbrida** Se todos os seus usuários do Skype for Business estão atualmente online ou no local ou se você tem uma combinação atualmente, você deve concluir as etapas para configurar uma implantação híbrida do Skype for Business Server ou do Lync Server 2013, conforme descrito em Implantar conectividade híbrida entre o Skype for Business Server e o [Office 365.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md) Para obter mais informações sobre implantações híbridas, consulte Planejar conectividade híbrida entre [o Skype for Business Server e o Office 365.](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 

    Se você estiver usando o Lync Server 2013, consulte [Lync Server 2013 híbrido.](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)

- **(Recomendado) Serviços de Federação do Active Directory (AD FS).** Recomendamos implantar o AD FS para dar suporte ao Single Sign-on. Para obter mais informações, [consulte Serviços de Federação do Active Directory (AD FS).](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx)

Para obter informações sobre como implantar o Sistema de Telefonia, consulte Habilitar usuários para o Sistema de Telefonia com conectividade [PSTN](enable-users-for-phone-system.md)local no Skype for Business Server.


