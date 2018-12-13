---
title: Consolidação de nuvem para equipes e Skype para negócios
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este artigo descreve como atingir essa consolidação para organizações com implementação (ões) de local do Skype para negócios (ou Lync) que está procurando mover para mover sua carga de trabalho UC para equipes e/ou Skype para negócios Online.
ms.openlocfilehash: 09a19b884b67f9d6c3dbbe552f2576b6b5e68674
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247609"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidação de nuvem para equipes e Skype para negócios

> [!Note]
> Este é um recurso de versão prévia ou lançamento antecipado. 

Muitas empresas de grandes porte tem mais de um no local floresta do AD e, em alguns casos, os clientes têm mais de um Exchange e/ou Skype para implantação de servidor de negócios (ou do Lync Server). Além disso, mesmo as organizações com somente uma floresta local acabaram em uma situação semelhante por meio de uma empresa fusão ou aquisição. À medida que esses clientes move para a nuvem, eles querem consolidar várias instâncias de uma carga de trabalho em determinado local para a nuvem em um único locatário do Office 365. Este artigo descreve como atingir essa consolidação para organizações com várias implantações de local do Skype para negócios (ou Lync) que deseja mover sua carga de trabalho UC para a nuvem da Microsoft, por exemplo, Microsoft Teams e/ou Skype para negócios Online.

Historicamente, a orientação foi para os clientes nesta situação consolidar os implantações no local e, em seguida, move para a nuvem. Embora essa ainda seja uma opção, este artigo descreve uma solução baseada em nova funcionalidade que permite que as organizações com vários Skype para implantações de negócios para migrar uma implantação ao mesmo tempo em um único locatário do Office 365, sem fazer local consolidação. Observe que mesmo com essa nova funcionalidade, Skype para Business Online e Teams da Microsoft não suporta vários Skype para florestas de negócios/Lync no modo híbrido com um único locatário do Office 365. 

> [!Important]
> Antes de usar este guia para a configuração, certifique-se examinar e compreender as [limitações](#limitations), como eles podem afetar a sua organização.

## <a name="overview-of-cloud-consolidation"></a>Visão geral da consolidação de nuvem

Consolidação de todos os usuários no local em nuvem em um único locatário do Office 365 pode ser alcançada para qualquer organização com vários Skype para implantações de negócios, desde que os principais requisitos a seguintes são atendidos:

- Deve haver no máximo um locatário do Office 365 envolvidos. Não há suporte para a consolidação em cenários com mais de um inquilino do Office 365.
- A qualquer momento determinado, somente um local Skype para a floresta de negócios pode estar em modo híbrido (Shared a espaço de endereço SIP). Todos os outro Skype local para florestas de negócios deve permanecer no local (e possivelmente federados uns com os outros). Observe que esses outro locais organizações *podem* sync para AAD se desejar com [novas funcionalidades para desabilitar os domínios SIP on-line](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponível a partir de dezembro de 2018.

Clientes com implantações do Skype para negócios em várias florestas devem totalmente migrar todos os usuários de um único híbrido Skype para a floresta de negócios individualmente para o inquilino do Office 365 usando a funcionalidade de espaço de endereçamento SIP compartilhado e, em seguida, desabilitar híbrida com que implantação no local, antes de seguir adiante para migrar o próximo local Skype para implantação de negócios. Antes de serem migrados para a nuvem, usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local mesmo do usuário.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemplo canônico da consolidação de nuvem

Considere a possibilidade de uma organização com dois separada federada implantações em instalações do Skype for Business que deseja consolidar o on-line no Microsoft Teams ou Skype para negócios Online.


|Detalhes do estado original |Detalhes do estado desejado |
|---------|---------|
|<ul><li>2 Skype independentes para negócios implantações em florestas separadas da AD local<li>No máximo 1 floresta está em híbrida com Skype para negócios Online <li> Organizações estão federadas uns com os outros <li>Os usuários não são sincronizados entre essas florestas<li> A organização pode ter um locatário do Office 365 e pode sincronizar seu diretório no Azure AD</ul>|<ul> <li>1 locatário do office 365<li>Não há mais local implantações, portanto, não há híbrida restantes<li>Todos os usuários no local são hospedados no Skype para Business Online e opcionalmente podem ser usuários somente equipes <li>Nenhum pegadas local em qualquer lugar do Skype para negócios <li>Os usuários ainda têm a autenticação no local</ul> |

![Consolidando duas separada federada implantações em instalações](../media/cloudconsolidationfig1.png)  

As etapas básicas para fazer a partir do estado original para o estado final desejado estão abaixo.  Observe que algumas organizações podem achar que seu ponto de partida é em algum lugar no meio estas etapas. Consulte [outros pontos de início](#other-starting-points), mais adiante neste artigo. Por fim, em alguns casos a ordem pode ser ajustada, dependendo da necessidade. [Restrições de chave e limitações](#limitations) são descritas posteriormente.

1.  Obtenha um locatário do Office 365 se ainda não existir.
2.  Verifique se que todos os domínios SIP relevantes, em ambas as implantações no local são verificados domínios do Office 365.
3.  Escolha um Skype para implantação de negócios que serão híbrida com o Office 365. Neste exemplo, usaremos OriginalCompany. <span>com.
4.  [Habilitar AAD conectar para a floresta](configure-azure-ad-connect.md) que se tornarão primeiro híbrida (OriginalCompany.<span> com). 
5.  Se você estará apresentando equipes em sua organização, defina a diretiva de todo o locatário para [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) para SfBWithTeamsCollab ou um dos outros SfB modos (SfBOnly ou SfBWithTeamsCollabAndMeetings). Isso é essencial para garantir o roteamento de chamadas e chats de usuários que mudar para equipes somente para usuários que permanecem no local.
6.  É recomendável nesse momento (mas ainda não é necessário até a etapa 11) para [Habilitar AAD conectar para outra floresta](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span> com). Presumindo que conecte AAD está habilitado nas duas florestas, pela organização se parece com **[Uma figura](#figure-a)**, que pode ser um ponto de partida comuns para algumas organizações. 
7.  Para todos os domínios SIP hospedados por outras implantações de local (neste caso, AcquiredCompany.<span> com) [desabilitar esses domínios SIP em Skype para Business Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) usando `Disable-CsOnlineSipDomain` no PowerShell. (Isto é a nova funcionalidade a partir de dezembro de 2018.)
8.  [Configurar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md) para OriginalCompany. <span>com (a uma implantação que ainda tiver habilitado online domínios SIP).
9.  Na implementação híbrida (OriginalCompany.<span> com), inicie a [migração de usuários do Skype for Business no local para a nuvem](move-users-between-on-premises-and-cloud.md) (se Teams somente ou não) para que a conta está hospedada no Skype para negócios Online. Agora que a organização é semelhante a **[Figura B](#figure-b)**. As principais alterações de A figura são:
    - Os usuários de ambos os diretórios de local estão no AAD.
    - AcquiredCompany. <span>com é um domínio SIP desabilitado online.
    - Alguns usuários foram movidos online para qualquer um dos Skype para equipes ou Business Online. (Consulte a usuário roxa.)
10. Depois que todos os usuários são movidos para a nuvem, [Desabilitar híbrida com o Skype para implantação no local de negócios](cloud-consolidation-disabling-hybrid.md) para OriginalCompany. <span>do Office 365:  
    - Desabilite a divisão de domínios no Office 365 inquilino.
    - Desabilite a capacidade de se comunicar com o Office 365 em OriginalCompany. <span>com local.
    - Atualize registros DNS para OriginalCompany. <span>com para apontar para o Office 365.
11. Se não tiver feito isso, [Habilitar AAD conectar-se para a próxima floresta](cloud-consolidation-aad-connect.md) que irão híbrida (AcquiredCompany.<span> com). Neste ponto, a organização é semelhante a **[Figura C](#figure-c)**. Isso pode ser outro ponto de partida comuns para algumas organizações. 
12. No PowerShell, [Permitir que os domínios SIP para a implantação próximo do local](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) que irão híbrido, AcquiredCompany. <span>com. Isso é feito usando `Enable-CsOnlineSipDomain`, que é a nova funcionalidade disponível a partir de dezembro de 2018.
13. Se você estiver usando a federação fechada, você deve adicionar todos os domínios SIP (excluindo *. microsoftonline.com) do puro online inquilino como domínios permitidos no **mesmo** Office 365. Observe que pode levar algum tempo antes da alteração entrará em vigor e não há nenhuma danos ao fazer isso, no início, portanto sugerimos fazer isso bem antes de passar para a etapa 14.
14. Atualize o ambiente local para aceitar todos os domínios SIP do inquilino online, portanto, eles devem ser iguais.
    - [Atualização de SAN em todos os certificados de borda](cloud-consolidation-edge-certificates.md) a ser o mesmo valor como antes, além de valores para quaisquer domínios SIP existentes e online (exceto *. microsoftonline.com), neste caso, Sip.OriginalCompany. <span>com.
    - Certifique-se de que OriginalCompany. <span>com é uma [permissão de domínio](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) na implantação do local, AcquiredCompany. Adicione domínios permitidos.
15. [Habilitar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md) entre AcquiredCompany local. <span>com e a nuvem.
16. Como desejado, [migrar usuários no local para a nuvem](move-users-between-on-premises-and-cloud.md). Você pode migrar usuários seja diretamente para [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) modo ou você pode migrá-los primeiro para Skype para negócios Online. Durante esse estado, a organização é semelhante a **[Figura D](#figure-d)**.
17. Depois que todos os usuários são migrados, [Desabilitar híbrida com o ambiente local](cloud-consolidation-disabling-hybrid.md) para *tornar a nuvem puro organização*!

Os diagramas abaixo mostram a configuração em vários pontos chaves durante esse processo.

##### <a name="figure-a"></a>Figura r:

- Ambos os sync organizações via AAD se conectar, portanto AAD agora tem todos os usuários de ambos implantações no local.
- Todos os usuários hospedados no local.  
- Skype para negócios híbrido ainda *não* estiver configurado.
- Se os usuários em qualquer implantação utilizar equipes, eles não poderão se federar umas às outras (ou qualquer organização), nem eles terão interoperabilidade com qualquer Skype para usuários comerciais. Enquanto estiver no estágio, a Microsoft recomenda usando apenas o equipes para canais.<br><br>
    ![Diagrama de uma figura](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura b:

- AcquiredCompany. <span>com é um domínio SIP [desabilitado](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) online. Todos os usuários estão no local. Se eles usarem equipes não têm federação ou interoperabilidade. Enquanto estiver no estágio, a Microsoft recomenda usando apenas o equipes para canais.
- Skype para negócios híbrido foi habilitado para uma das organizações local.
- Alguns usuários na organização híbrida foram movidos para a nuvem (usuário conforme indicado pelo sombreamento roxo). Esses usuários podem ser Skype para usuários corporativos Online ou equipes somente os usuários com suporte de Federação e interoperabilidade completa.<br><br>
    ![Diagrama da Figura B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura c:

- Todos os usuários do OriginalCompany. <span>com agora estão na nuvem (hospedada no Skype para Business Online). É recomendável que eles também sejam equipes apenas.
- Skype para configuração híbrida de negócios com o OriginalCompany. <span>implantação com tiver sido desativada. A implantação local desapareceu.
- Se AcquiredCompany. <span>com anteriormente não era está sincronizando para AAD, para continuar a partir aqui ele precisa ser sincronizados agora. Mas ainda não estiver híbrida (espaço de endereçamento SIP compartilhado) e até que a organização esteja pronta para migrar para o híbrido, o domínio SIP on-line para a organização local puro (AcquiredCompany.com) deve permanecer desabilitado, para que os usuários de equipes online podem se comunicar com usuários locais.<br><br>
    ![Diagrama da Figura C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura d:

- AcquiredCompany. <span>com agora está habilitada como um domínio SIP online.
- Local é atualizado para aceitar OriginalCompany. <span>com. (Ambos permitidas domínio e certificados de borda são atualizados).
- Espaço de endereço SIP compartilhado é habilitado entre AcquiredCompany. <span>locatário do Office 365 e com.
- Alguns usuários na organização híbrida podem ter sido movidos para a nuvem, como usuário D abaixo (indicada por sombreamento roxo).<br><br>
    ![Figura D diagrama](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Outros pontos de início

As etapas no exemplo canônico acima pressupõem que a organização começa com duas implantações de locais federados com nenhum presença do Office 365. No entanto, algumas organizações podem ter um espaço existente do Office 365 e pode haver pontos de entrada diferentes na sequência acima. Há quatro configurações típicas:

- Organizações de vários locais federados com nenhum locatário do Office 365. Nesse caso, inicie na etapa 1.
- Várias organizações de local federado que já estão sincronizando vários Skype para a floresta de negócios em um único Azure AD de inquilinos. Uma organização desse tipo é semelhante a organização hipotética na Figura A, que concluiu as etapas 1 a 6 e deve ser iniciada na etapa 7.
- Uma organização híbrida que agrupa com 1 ou mais outras organizações de local puro, sendo que nenhum deles se sincronizar com o AAD. Uma organização como essa seria semelhante a organização hipotética na **Figura F**, mostrado abaixo.
    - Esta organização é semelhante à Figura B, que concluiu as etapas 1 a 9, exceto:
        - Seu Skype não híbridas para implantações de negócios são *não* ainda está sincronizando para o Windows Azure AD.
        -  Domínios SIP online ainda não estejam desabilitados. 
    - Essas organizações deverá:
        - Concluir a migração da organização híbrida existente e digite a sequência acima na etapa 10.  OR,
        - Se ele for desejado para sincronizar qualquer outro Skype para florestas de negócios em AAD antes de concluir a migração da organização híbrida, então a organização deve executar etapa 7 (desabilitar online todos os domínios SIP em qualquer outro local Skype para implantação de negócios que será sincronização em AAD) e, em seguida, habilitar AAD conectar e só então continuar com a etapa 10 (encerre a implantação híbrida original).       
                **Figura F**<br>
                ![Figura f diagrama](../media/cloudconsolidationfige.png)
- Skype puro para a organização Business Online (que pode ou não pode estar usando equipes) que agrupa com Skype um local separado para a organização de negócios. Depois que essa organização desabilita o domínio SIP on-line para a organização local e habilita AAD conectar-se para o Skype local para a organização de negócios, ele se parece com a organização hipotética mostrada na **[Figura C](#figure-c)** que concluiu as etapas 1-11.

## <a name="limitations"></a>Limitações

- Deve haver no máximo um locatário do Office 365 envolvidos. Não há suporte para a consolidação em cenários com mais de um inquilino do Office 365.
- Somente um local Skype para a floresta de negócios pode ser no modo híbrido (espaço de endereçamento SIP compartilhado) ao mesmo tempo. Todos os outros locais Skype para florestas de negócios deve permanecer puramente no local e deve ser federado com umas às outras e inquilino do Office 365.
- Antes de serem migrados para a nuvem, há uma experiência assimétrica para os usuários nesta implantação, porque nem todos os usuários no online são representados no local:
    - A experiência pode ser somada da seguinte maneira:
        - Qualquer usuário hospedado online vão interagir com os usuários locais no ambiente híbrido, como se o usuário é híbrido.
        - Os usuários do local na implementação híbrida vão interagir com usuários online que são representados no seu diretório local como se fossem híbrida. 
        - Os usuários na implementação híbrida vão interagir com usuários online que não são representados no local AD local conforme federados.
    - Na **[Figura D](#figure-d)** acima, o usuário f é local em AcquiredCompany. <span>com.  Usuário f vai interagir com o usuário D (hospedados online) usando a experiência híbrida standard, mas o usuário f terão uma experiência federada com usuários A, B e C porque elas não são representadas no diretório local. No entanto, os usuários A, B e C vão interagir com o usuário E como se o usuário estivesse em híbrida.
    - Implicações de interação sendo híbrida versus Federação:
        - Presença não está automaticamente inscrito para que usuários federados, a menos que o usuário está marcado como um contato.
        - Encaminhamento de chamadas não funciona entre domínios federados.
        - Cenários de transferência de chamada são mais limitados.
        - Limitação pode ser aplicada ao tráfego federado.
- Dado essa experiência assimétrica, suporte oficial para a funcionalidade de chamada em cenários locais cruzados entre um usuário local e um usuário de nuvem que não é no diretório local é limitado para apenas ponto a ponto. 
    - Chamar o encaminhamento, transferência, filas de chamada, etc. entre esses usuários não é suportada.
    - Esses cenários de chamada não suportados ainda aparecerão habilitados, mas em muitos casos irá falhar maneiras imprevisível. 
    - Na **[Figura D](#figure-d)** acima, usuário E está no local e chamadas com os usuários A, B ou C terá suporte somente como ponto a ponto. (Chamadas com o usuário D não terá limitações de suporte.)  No entanto, depois que o usuário local f é movido para a nuvem, essa restrição não se aplica.
- Se você tiver mais de uma implantação do Skype para Business Server 2019 em seu ambiente, 1 somente desses implantação pode ser configurado para usar o atendedor automático organizacional, já que esse recurso exige Skype para configuração do servidor de negócios híbrida. 
- A ordem de algumas das etapas anteriores pode ser ajustada. O requisito fundamental que deve ser atendido é que, se todos esses são verdadeiras:
    - Mais de um local Skype para negócios floresta está sincronizando para um único locatário AAD
    - Domínio dividido está habilitado com uma floresta local
    - Pelo menos um usuário na organização híbrida ter sido migrado para a nuvem<br>   Em seguida, você *deve* desabilitar todos os outros domínios SIP online a partir de qualquer outro local Skype para a floresta de negócios. Caso contrário, Federação entre usuários online na híbrido local e organização usuários em outras organizações serão interrompidos em uma direção.

## <a name="implications"></a>Implicações

- Porque há limitações no suporte para recursos avançados de chamada, conforme descrito acima, **organizações devem tratar desses estados assimétricos como transitórios como parte da migração e não buscá-las como estável**.  
- Organizações com vários Skype local para implantações de negócios geralmente devem começar com uma implantação que pode ser migrada totalmente para a nuvem, para que possa continuar a consolidação. Ele é compreendido que em alguns casos haverá holdouts de determinados grupos de usuários para o qual ele ainda não é viável para mover para equipes. Quando isso for uma consideração em cenários que envolvem várias Skype para florestas de negócios, inicie migrando com outra floresta que não tem estas limitações, se possível.
- Ao se mover no local para a nuvem, os usuários que possuem relacionamentos de delegação e/ou são geralmente estão envolvidos nos cenários devem ser movidos juntos como uma unidade de encaminhamento de chamadas.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerações sobre a transferência para o modo de TeamsOnly

Quando você move os usuários no local para a nuvem em um ambiente híbrido, você poderá movê-los para qualquer Skype para o modo de negócios apenas ou TeamsOnly. *Se você planeja mover usuários para o modo de TeamsOnly, certifique-se de ler esta seção primeiro.*

- Quando você atribui TeamsOnly de modo a um usuário, todos os bate-papos e chamadas de qualquer outro usuário land no cliente de equipes desse usuário. 
- Para garantir o roteamento apropriado de bate-papos e chamadas entre usuários que estão TeamsOnly e usuários que ainda estão usando Skype for Business no local, você deve garantir que usuários locais tenham TeamsUpgradePolicy com um dos modos de SfB, em vez de ilhas (que é o padrão ). 
    - Para fazer isso, *que primeiro, você deve definir a instância global do seu locatário do TeamsUpgradePolicy para um destes valores*:
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Você pode conceder a política de Inquilino usando este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Observação: No momento, você deve fazer isso em um nível de locatário porque a diretiva não pode ser atribuída a usuários individuais que não têm um endereço SIP no diretório online. Enquanto você desabilitou online domínios SIP para sua implementação do local puro (ões), usuários nesses domínios não terão endereços SIP no diretório online por design. Daí, a única maneira de aplicar a política aos usuários no local é, atribuindo-se no nível do locatário. Por outro lado, in a hybrid deployment usuários terão um endereço SIP no diretório online para que eles podem ser atribuídos explicitamente uma política se ele for desejado que têm um valor diferente da política global de locatário.
- O cliente de equipes eu ainda não atendê-os modos de SfB de TeamsUpgradePolicy. Por exemplo, quando estiver nesses modos, iniciação chamada e bate-papo em equipes é atualmente possível, embora no futuro que não será o caso. Isso pode causar confusão entre usuários porque respostas em alguns casos, talvez land em equipes e às vezes Skype para os negócios, dependendo das circunstâncias. É recomendável que você separadamente desabilitar chamada e chat via TeamsMessagingPolicy e TeamsCallingPolicy para usuários que ainda estão no local.

## <a name="see-also"></a>Consulte também

[Atualizar o certificado de borda](cloud-consolidation-edge-certificates.md)

[Atualizar AAD conectar para incluir mais de uma floresta](cloud-consolidation-aad-connect.md)

[Desabilitar híbrido para concluir a migração para a nuvem](cloud-consolidation-disabling-hybrid.md)