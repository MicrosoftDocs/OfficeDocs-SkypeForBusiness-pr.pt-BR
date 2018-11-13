---
title: Planejar a conectividade híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Considerações de planejamento para a implementação de conectividade híbrida entre Skype para Business Server e do Skype para Business Online ou equipes.
ms.openlocfilehash: 34df2639ed57376549b2a8bde2e4b0e071d08957
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295270"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planejar a conectividade híbrida entre Skype para Business Server e Office 365

## <a name="overview"></a>Visão geral

Leia este tópico para saber como planejar a conectividade híbrida entre Skype para Business Server e do Skype Business Online ou equipes. A configuração da conectividade híbrida é a primeira etapa da implantação de muitas soluções híbridas do Skype for Business.

Soluções híbridas permitem reter algum controle local, também beneficiando dos serviços online fornecidas em nuvem da Microsoft. Com conectividade híbrida configure e uma variedade de usuários locais e de serviços em nuvem para sua online, você pode escolher mover os usuários para a nuvem com base em sua necessidade de agenda e corporativos.

Por exemplo, você pode optar por fazer o controle de chamada pelo sistema de telefone da Microsoft na nuvem enquanto mantém a conectividade de PSTN do local. Você também pode optar por tirar proveito de outros serviços de nuvem, como caixa postal de nuvem e o conector de dados da chamada.

Este tópico descreve os requisitos de infraestrutura e sistema, que você precisará configurar a conectividade híbrida entre seu Skype local existente para implantação de servidor de negócios – com usuários que foram criados no seu local do Active Directory – e Skype para negócios on-line ou equipes.

Depois que você leia este tópico e estiver pronto para configurar a conectividade híbrida, consulte [Configure a conectividade de híbrido entre Skype para Business Server e Office 365](configure-hybrid-connectivity.md). Os tópicos de configuração fornecem orientação passo a passo para configurar a conectividade híbrida entre sua implantação no local e Skype para negócios Online.

(Para obter informações sobre como configurar o Lync Server 2013 ou a implantação do Lync Server 2010 para o híbrido, consulte [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

## <a name="split-domain-functionality"></a>Funcionalidade de domínio dividido
<a name="BKMK_Overview"> </a>

 Com a conectividade híbrida configurada entre uma implantação local do Skype para Business Server e Skype para equipes ou Business Online, você pode ter alguns usuários hospedados no local e alguns usuários hospedagem online.

Esse tipo de configuração, às vezes, é conhecido como "domínio dividido" – que significa que os usuários de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e Skype para Business Online ou equipes, conforme mostrado no diagrama a seguir:

![Conectividade híbrida do SfB - domínio dividido](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Com um ambiente de domínio dividido:

- Os usuários hospedados no local interagem com Skype local para os servidores de negócios. Eles também podem ter acesso aos serviços online, como caixa postal de nuvem.

- Os usuários hospedados online podem interagir com Skype para negócios ou equipes de serviços online.

- Os usuários de ambos os ambientes podem colaborar entre si por meio de mensagens instantâneas, participando de chamadas em conferência ou chamadas VoIP e assim por diante.

- Azure Active Directory se conectar é usado para sincronizar seu diretório local com o Office 365.

O Active Directory local é autoritativo, o que quer dizer que você deve fazer o seguinte para garantir que os usuários no local e online possam detectar uns aos outros:

- Todos os usuários devem ser criados no Active Directory local primeiro e, em seguida, sincronizados com o Azure AD.

- Usuários que estejam mudando para a nuvem devem ter um dos Skype uma licença de negócios plano 2 ou equipes.

- Se quiserem que seus usuários para se beneficiar dos recursos online adicionais, como transmissão do Skype reunião ou caixa postal de nuvem, você precisará atribuí-las a licença apropriada no Office 365.

- Depois que os usuários do Skype for Business Online tiverem uma licença atribuída a eles, será necessário habilitá-los para o Skype for Business ou para o Enterprise Voice local. Para obter mais informações, consulte [habilitar os usuários para o Enterprise Voice no local](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Para obter mais informações sobre os requisitos do Hybrid Voice, consulte [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).


## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
<a name="BKMK_Infrastructure"> </a>

Para implementar a conectividade híbrida entre seu ambiente local e serviços de comunicação do Office 365, você precisa atender aos seguintes requisitos de infraestrutura.

- Uma única implantação do Skype para Business Server ou o Lync Server é implantado em uma topologia com suporte no local. Consulte [requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) neste tópico.

- Um inquilino do Microsoft Office 365 com o Skype para Business Online habilitado.

    > [!NOTE]
    > Você só pode usar um único locatário para uma configuração híbrida com sua implantação local.

- Skype para ferramentas administrativas do servidor de negócios. (Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, você pode usar as ferramentas administrativas do Lync Server 2013. Para obter mais informações, consulte [Lync Server 2013 híbrido](https://go.microsoft.com/fwlink/p/?LinkId=617360).)

- Azure Active Directory Connect para sincronizar seu diretório local com o Office 365. Para obter mais informações, consulte [Connect do Azure AD: contas e permissões](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Para oferecer suporte ao logon único no Office 365 de modo que os usuários possam usar as mesmas credenciais de logon que no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect. É possível também usar Serviços de Federação do Active Directory (AD FS) para login único com o Office 365. 

Para configurar a conectividade híbrida, você também precisará configurar a federação entre seu local e ambientes on-line e configurar sua Skype para locatário Business Online para um espaço de endereçamento compartilhado do protocolo de iniciação de sessão (SIP). Para obter mais informações sobre as etapas necessárias para configurar a conectividade híbrida, consulte [Configure conectividade de híbrida](configure-hybrid-connectivity.md).

Depois de configurar conectividade híbrida, você pode mover usuários para Skype para equipes ou Business Online. Para obter mais informações, consulte [mover os usuários no local para Skype para Business Online](move-users-from-on-premises-to-skype-for-business-online.md) e [mover os usuários no local para equipes](move-users-from-on-premises-to-teams.md).

## <a name="multi-forest-support"></a>Suporte a várias florestas
<a name="BKMK_MultiForest"> </a>

Os usuários poderão acessar as funcionalidades do Skype for Business em outra floresta se os seguintes requisitos forem atendidos:

- Os usuários são sincronizados corretamente na floresta que hospeda o Skype for Business: em configurações híbridas, isso quer dizer que os usuários devem ser sincronizados como objetos de usuários desabilitados.

- A floresta que hospeda o Skype for Business deve confiar na floresta que contém os usuários.

Para obter detalhes sobre os cenários de híbrida em várias florestas, consulte [Configure um ambiente de várias floresta para o híbrido Skype para negócios](configure-a-multi-forest-environment-for-hybrid.md).

## <a name="administrator-credentials"></a>Credenciais do administrador
<a name="BKMK_Credentials"> </a>

Quando você é solicitado a fornecer suas credenciais de administrador, use o nome de usuário e a senha da conta de administrador para o seu locatário do Office 365. Você também usará essas credenciais ao configurar o Azure Active Directory para federação, sincronização de diretórios, logon único e mover os usuários Skype para Business Online.

## <a name="skype-for-business-online-powershell"></a>PowerShell do Skype for Business Online
<a name="BKMK_PowerShell"> </a>

Agora, os administradores têm a capacidade de usar o Windows PowerShell para gerenciar o Skype para Business Online e seu Skype para contas de usuário Business Online. Para fazer isso, você deve primeiro baixar e instalar o Skype para negócios on-line do módulo do conector do Microsoft Download Center. Para obter mais informações sobre como baixar, instalar e usando o Skype para negócios on-line do módulo do conector e para obter informações detalhadas sobre usando o Windows PowerShell para gerenciar Skype para Business Online, consulte [Configurar o computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Suporte ao cliente do Skype for Business
<a name="BKMK_ClientSupport"> </a>

Existem algumas diferenças entre os recursos com suporte em clientes e os recursos disponíveis em ambientes locais e online. Os seguintes clientes compatíveis com Skype para Business Online em uma implantação híbrida:

- Skype for Business

- Lync 2013

- Lync 2010

- Aplicativo Lync Windows Store

- Lync Web App

- Lync Mobile

- Lync para Mac 2011

- Sistema de sala de Lync e Skype para o sistema de sala de negócios

- Lync Basic 2013

- Microsoft Surface Hub

Antes de decidir onde você deseja usuários domésticos em sua organização, você deve consultar a [comparação de recursos do cliente de Desktop do Skype para a empresa](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) para determinar o suporte de cliente para as diversas configurações do Skype para Business Server. Consulte também:

- [Planejar clientes e dispositivos](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparação de recursos do cliente móvel para Skype para negócios](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Requisitos de topologia
<a name="BKMK_Topology"> </a>

Para configurar sua implantação para o híbrido com Skype para Business Online, você precisa ter uma das seguintes topologias com suporte:

- Um Skype para implantação de negócios Server 2015 com todos os servidores que executam o Skype para Business Server 2015.

- Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.

    Para conectividade de voz híbrida, o servidor de borda é designado como borda de federação deve ser Skype para negócios 2015; a borda também requer um Skype para back-end do servidor de negócios. Você deve ter um pool sem usuários.

- Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as últimas atualizações acumuladas.

  - O servidor de borda de Federação e o servidor de próximo salto da federação servidor de borda devem estar executando o Lync Server 2010 com as últimas atualizações acumuladas.

  - O Skype para Business Server 2015 ou o Lync Server 2013 Administrative Tools deve ser instalado em pelo menos um servidor ou estação de trabalho de gerenciamento.

- Um misto Skype para implantação Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype para Business Server 2015 e Lync Server 2013:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition. 

  - O Pool de Diretores associado à federação SIP, se ela existir.

  - O Pool de Borda associado à federação SIP.

- Um misto Skype para implantação Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype para Business Server 2015 e Lync Server 2010:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition. 

  - O Pool de Diretores associado à federação SIP, se ela existir.

  - O Pool de Borda associado à federação SIP do site.

- Uma implantação mista de Lync Server 2010 e Lync Server 2013 com as seguintes funções de servidor em pelo menos um site executando o Lync Server 2013:

  - Pelo menos um servidor Pool Enterprise ou Standard Edition no site.

  - O Pool de Diretores associado à federação SIP, se ela existir no site.

  - O Pool de Borda associado à federação SIP do site.

## <a name="federation-allowedblocked-lists-requirements"></a>Requisitos das listas de permissões/bloqueios da federação
<a name="BKMK_Federation"> </a>

A lista Domínios permitidos contém domínios com um FQDN (nome de domínio totalmente qualificado) de Borda parceiro configurado. Por vezes, eles são chamados de servidores parceiros permitidos ou parceiros de federação diretos. Você deve estar familiarizado com a diferença entre a federação aberta e a federação fechada, conhecidas respectivamente como descoberta de parceiros e lista de domínios dos parceiros permitidos nas implantações locais.

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

- O domínio correspondente deve ser o mesmo configurado para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para seu locatário online. Caso contrário, a federação fechada deverá ser configurada para seu locatário online.

- A lista de domínios bloqueados da implantação local deve corresponder exatamente à do seu locatário online.

- A lista de domínios permitidos da implantação local deve corresponder exatamente à do seu locatário online.

- Federação deve ser habilitada para as comunicações externas para o locatário online, que é definida por meio do Skype para painel de controle corporativos Online.

## <a name="dns-settings"></a>Configurações de DNS
<a name="BKMK_DNS"> </a>

Ao criar registros DNS para implantações híbridas, todos os Skype para registros DNS externos corporativos deve apontar para a infraestrutura local. Para obter detalhes sobre registros DNS necessários, consulte [requisitos de DNS para Skype para Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Além disso, você precisará garantir que a resolução de DNS descrita na tabela a seguir funciona em sua implantação no local:

|Registro DNS  <br/> |Pode ser resolvido por  <br/> |Requisitos de DNS  <br/> |
|:-----|:-----|:-----|
|Registro SRV de DNS para _sipfederationtls._tcp. \<sipdomain.com\> para todas as compatíveis domínios SIP resolver em IP(s) de borda de acesso externo  <br/> |Servidor(es) de borda  <br/> |Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP que está dividido entre as instalações local e online.  <br/> Deve usar uma correspondência estrita de nomes DNS entre o domínio no nome de usuário e o registro SRV.  <br/> |
|Registro(s) A de DNS para FQDN do serviço de webconferência de borda, como webcon.contoso.com, que resolve IP(s) de borda de webconferência  <br/> |Rede corporativa interna conectados nos computadores dos usuários  <br/> |Habilitar usuários online para apresentar ou visualizar conteúdo em reuniões hospedadas localmente. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e observações compartilhadas.   <br/> |

Dependendo de como o DNS está configurado na sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para proporcionar resolução de DNS interna para esses registros.

## <a name="firewall-considerations"></a>Considerações sobre o firewall
<a name="BKMK_Firewall"> </a>

Os computadores de sua rede devem ser capazes de realizar pesquisas DNS padrão na Internet. Se esses computadores puderem acessar os sites padrão da Internet, sua rede atenderá a esse requisito.

Dependendo do local do seu centro de dados do Microsoft Online Services, você também deve configurar os dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio de caractere curinga (por exemplo, todo o tráfego da \*. outlook.com). Se dos firewalls da organização não oferecer suporte a configurações de nome de curinga, você terá de determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.

Para obter mais informações, veja [URLs e intervalos de endereço IP do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Requisitos de porta e protocolo
<a name="BKMK_Ports"> </a>

Além dos requisitos de porta para a comunicação interna, você também deve configurar as portas a seguir para habilitar a conectividade híbrida.


|**Protocolo**|**TCP ou UDP**|**IP de origem**|**IP de destino**|**Porta de origem**|**Porta de destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Borda de Acesso  <br/> |Office 365  <br/> |Qualquer  <br/> |5061  <br/> |Sinalização  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Borda de Acesso  <br/> |Qualquer  <br/> |5061  <br/> |Sinalização  <br/> |
|STUN  <br/> |TCP  <br/> |Borda A/V  <br/> |Office 365  <br/> |50000-59999  <br/> |443, 50000-59999  <br/> |Abertas para sessões de áudio, vídeo e compartilhamento de aplicativos  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Borda A/V  <br/> |443  <br/> |50000-59999  <br/> |Abertas para sessões de áudio, vídeo e compartilhamento de aplicativos  <br/> |
|STUN  <br/> |UDP  <br/> |Borda A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Abertas para sessões de áudio, vídeo  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Borda A/V  <br/> |3478  <br/> |3478  <br/> |Abertas para sessões de áudio, vídeo  <br/> |

Para obter mais informações sobre a porta e firewall de planejamento para o servidor de borda, consulte [requisitos de ambiente de servidor de borda no Skype para Business Server](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Consulte também [Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md) e o [Diagrama de cargas de trabalho dos protocolos](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Dados e contas de usuário
<a name="BKMK_UserAccounts"> </a>

Em uma implantação híbrida, qualquer usuário que você deseja hospedar online deve primeiro ser criado na implantação do local, para que a conta de usuário é criada nos serviços de domínio Active Directory. Em seguida, você pode mover o usuário para Skype para negócios Online, que irá mover a lista de contatos do usuário.

Ao sincronizar contas de usuário entre sua implantação no local e online inquilino usando AAD conectar, você precisa sincronizar as contas do AD para todos os Skype para usuários corporativos ou o Lync em sua organização, mesmo se os usuários não são movidos para online. Se você não sincronizar todos os usuários, a comunicação entre os usuários online e locais em sua organização poderá não funcionar como esperado.

> [!IMPORTANT]
> Gerenciamento de todos os usuários, incluindo o usuário move entre locais e do Skype para negócios Online, deve ser feito usando a última versão instalada das ferramentas administrativas. As ferramentas administrativas devem ser instaladas em um servidor separado que possui acesso se conectam a implantação existente do local e à Internet. O cmdlet para mover usuários de sua implantação no local para Skype para negócios Online, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), deve ser executado em Ferramentas administrativas conectadas à sua implantação no local. Para obter mais informações sobre como mover usuários, consulte [mover os usuários no local para Skype para negócios Online](move-users-from-on-premises-to-skype-for-business-online.md).

Você também deve considerar os seguintes problemas relacionados ao usuário durante o planejamento para uma implantação híbrida:

- **Contatos do usuário** O limite de contatos para usuários do Lync Online é 250. Todos os contatos além desse número serão removidos da lista de contatos do usuário quando a conta é movida para o Lync Online.

- **Mensagens instantâneas e presença** Listas de contatos do usuário, grupos e listas de controle de acesso (ACLs) são migradas com a conta de usuário.

- **Dados de conferência, o conteúdo das reuniões e reuniões agendadas** Este conteúdo não é migrado com a conta de usuário. Os usuários devem reagendar as reuniões depois que as contas são migradas para o Lync Online.

## <a name="user-policies-and-features"></a>Recursos e políticas de usuário
<a name="BKMK_UserPolicies"> </a>

- Em um ambiente híbrido, os usuários podem estar habilitados para o sistema de mensagens instantâneas e conferências, no local (reuniões) ou online; porém, não para os dois ao mesmo tempo.

- **Suporte do cliente** Alguns usuários podem exigir uma nova versão do cliente quando eles são movidos para Skype para negócios Online. Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um Skype para pool Business Server ou o Lync Server 2013 antes da migração para o Skype para negócios Online.

- **Local políticas e configuração (não-usuários)** Online e políticas exigem configuração separado no local. Você não pode definir políticas globais que se apliquem a ambas.
