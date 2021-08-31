---
title: Consolidação de nuvem para Teams e Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Este artigo descreve como alcançar essa consolidação para organizações com implantações locais do Skype for Business (ou Lync) que estão procurando mover para mover sua carga de trabalho de UC para Teams.
ms.openlocfilehash: 99218c2a629a32d61e9625f8a7808d9f95e9f873
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731760"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidação na nuvem para o Teams e Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Muitas grandes empresas têm mais de uma floresta local do AD e, em alguns casos, os clientes têm mais de uma implantação do Exchange e/ou do Skype for Business Server (ou do Lync Server). Além disso, até mesmo as organizações com apenas uma floresta local podem se encontrar em uma situação semelhante no caso de fusões ou aquisições empresariais. À medida que esses clientes se movem para a nuvem, eles querem consolidar as várias instâncias de uma determinada carga de trabalho local na nuvem em uma única Microsoft 365 organização. Este artigo descreve como alcançar essa consolidação para organizações com várias implantações locais do Skype for Business (ou Lync) que querem mover sua organização inteiramente para Microsoft Teams (todos os usuários são Teams Somente).

Historicamente, a orientação era a de que clientes nessa situação deviam consolidar as implantações no local primeiro e depois migrar para a nuvem. Embora ainda seja uma opção, este artigo descreve uma solução que permite que as organizações com várias implantações de Skype for Business migrem uma implantação por vez para uma única organização Microsoft 365, sem fazer a consolidação local. Observe que Microsoft Teams não dá suporte a várias florestas Skype for Business ou Lync Server no modo híbrido com uma única organização Microsoft 365. 

> [!Important]
> Antes de usar este guia para configuração, revise e entenda [as](#limitations)Limitações, pois elas podem afetar sua organização.

## <a name="overview-of-cloud-consolidation"></a>Visão geral da consolidação na nuvem

A consolidação de todos os usuários do local para a nuvem em uma única organização Microsoft 365 pode ser alcançada para qualquer organização com várias implantações Skype for Business, desde que os seguintes requisitos principais sejam atendidos:

- Deve haver no máximo uma organização Microsoft 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
- Em qualquer momento, somente uma floresta do Skype for Business local pode estar no modo híbrido (Espaço de Endereçamento SIP Compartilhado). Todas as outras florestas locais do Skype for Business devem permanecer no local (e supostamente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com o Azure AD, se desejar, se você desabilitar  [domínios SIP online.](/powershell/module/skype/disable-csonlinesipdomain)

Os clientes com implantações do Skype for Business em várias florestas devem Skype for Business migrar totalmente todos os usuários de uma única floresta híbrida individualmente para Microsoft 365 organização do Microsoft 365 usando a funcionalidade Espaço de Endereço SIP Compartilhado e, em seguida, desabilitar o híbrido com essa implantação local, antes de migrar a próxima implantação local Skype for Business implantação. Antes de serem migrados para a nuvem, os usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local do mesmo usuário.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemplo canônico de consolidação de nuvem

Considere uma organização com duas implantações locais federadas separadas Skype for Business que deseja consolá-las online no Microsoft Teams.


|Detalhes de estado originais |Detalhes de estado desejados |
|---------|---------|
|<ul><li>2 implantações Skype for Business locais independentes em florestas separadas do AD<li>No máximo 1 floresta está híbrida com Teams <li> As organizações são federadas umas com as outras <li>Os usuários não são sincronizados entre essas florestas<li> A organização pode ter uma organização Microsoft 365 e pode estar sincronizando seu diretório no Azure AD</ul>|<ul> <li>1 Microsoft 365 organização<li>Sem mais implantações locais, portanto, nenhum híbrido restante<li>Todos os usuários do local foram movidos para o Teams somente <li>Nenhuma pegada local de Skype for Business Server em qualquer lugar <li>Os usuários ainda têm autenticação local</ul> |

![Consolidando duas implantações locais federadas separadas.](../media/cloudconsolidationfig1.png)  

As etapas básicas para obter do estado original para o estado final desejado estão abaixo.  Observe que algumas organizações podem descobrir que seu ponto de partida está em algum lugar no meio dessas etapas. Consulte [Outros pontos de partida](#other-starting-points), posteriormente neste artigo. Por fim, em alguns casos, a ordem pode ser ajustada, dependendo da necessidade. [Restrições e limitações principais](#limitations) são descritas posteriormente.

1.  Obter uma Microsoft 365 se ainda não existir.
2.  Certifique-se de que todos os domínios SIP relevantes em ambas as implantações locais sejam verificados Microsoft 365 domínios.
3.  Escolha uma Skype for Business implantação que será híbrida com Microsoft 365. Neste exemplo, vamos usar OriginalCompany. <span> com.
4.  [Habilita o Conexão AAD para a floresta](configure-azure-ad-connect.md) que se tornará híbrida pela primeira vez (OriginalCompany. <span> com). 
5.  Demarque a política de todo o locatário para [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) como SfBWithTeamsCollab ou um dos outros modos SfB (SfBOnly ou SfBWithTeamsCollabAndMeetings). Isso é fundamental para garantir o roteamento de chamadas e chats de usuários que se movem para Teams somente para usuários que permanecem no local.
6.  É recomendável neste ponto (mas ainda não necessário até a etapa 11) habilitar o [AAD Conexão para](cloud-consolidation-aad-connect.md) a outra floresta (AcquiredCompany. <span> com). Supondo que Conexão AAD está habilitado em ambas as florestas, a organização se parece com **[a Figura A](#figure-a)**, que pode ser um ponto de partida comum para algumas organizações. 
7.  Para quaisquer domínios SIP hospedados por outras implantações locais (neste caso, AcquiredCompany. <span> com), [desabilite esses domínios SIP](/powershell/module/skype/disable-csonlinesipdomain) online em sua organização Microsoft 365 usando no `Disable-CsOnlineSipDomain` módulo Teams PowerShell. 
8.  [Configure Skype for Business híbrido para](configure-federation-with-skype-for-business-online.md) OriginalCompany. <span> com (a única implantação que ainda habilita domínios SIP online).
9.  Na implantação híbrida (OriginalCompany. <span> com), comece [a mover](move-users-between-on-premises-and-cloud.md) usuários do Skype for Business local para a nuvem (Teams somente ou não) para que o usuário Teams Somente. Agora, a organização se parece **[com a Figura B](#figure-b)**. As principais alterações da Figura A são:
    - Os usuários de ambos os diretórios locais agora estão no AAD.
    - AcquiredCompany. <span> com é um domínio SIP online desabilitado.
    - Alguns usuários foram movidos online para Teams Somente. (Consulte o usuário roxo A.)
10. Depois que todos os usuários são movidos para a nuvem, desabilite a implantação híbrida [Skype for Business local](cloud-consolidation-disabling-hybrid.md) para OriginalCompany. <span> com de Microsoft 365:  
    - Desabilitar o domínio dividido na Microsoft 365 organização.
    - Desabilite a capacidade de se comunicar com Microsoft 365 em OriginalCompany. <span> com local.
    - Atualizar registros DNS para OriginalCompany. <span> com para apontar para Microsoft 365.
11. Se ainda não tiver sido feito, [habilita o AAD Conexão para](cloud-consolidation-aad-connect.md) a próxima floresta que será híbrida (AcquiredCompany. <span> com). Neste ponto, a organização se parece com **[a Figura C](#figure-c)**. Esse pode ser outro ponto de partida comum para algumas organizações. 
12. No Teams PowerShell, [habilita](/powershell/module/skype/enable-csonlinesipdomain) os domínios SIP para a próxima implantação local que será híbrida, AcquiredCompany. <span> com. Isso é feito usando `Enable-CsOnlineSipDomain` , que é uma nova funcionalidade disponível a partir de dezembro de 2018.
13. Se você estiver usando federação fechada, deverá adicionar quaisquer domínios SIP (excluindo .microsoftonline.com) do locatário online puro como Domínios Permitidos na mesma \* Microsoft 365.  Observe que pode levar algum tempo antes que a alteração entre em vigor e não haja nenhum dano ao fazer isso antecipadamente, portanto, sugerimos fazer isso com antecedência da etapa 14.
14. Atualize o ambiente local para aceitar quaisquer domínios SIP do locatário online, para que eles corresponderem.
    - [Atualize](cloud-consolidation-edge-certificates.md) a SAN em todos os certificados de borda para ter o mesmo valor de antes, além de valores para quaisquer domínios SIP online existentes (exceto *.microsoftonline.com), nesse caso, Sip.OriginalCompany. <span> com.
    - Certifique-se de OriginalCompany. <span> com é [um domínio permitido](/powershell/module/skype/new-csalloweddomain) na implantação local, AcquiredCompany. Adicionar domínios permitidos.
15. [Habilitar Skype for Business híbrido](configure-federation-with-skype-for-business-online.md) entre AcquiredCompany local. <span> com e a nuvem.
16. Conforme desejado, [migre usuários do local](move-users-between-on-premises-and-cloud.md) para a nuvem para se tornarem usuários do [TeamsOnly.](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) Durante esse estado, a organização se parece com **[a Figura D](#figure-d)**.
17. Depois que todos os usuários são migrados, [desabilite](cloud-consolidation-disabling-hybrid.md) o híbrido com o ambiente local para tornar a *organização uma nuvem pura!*

Os diagramas abaixo mostram a configuração em vários pontos-chave durante esse processo.

##### <a name="figure-a"></a>Figura A:

- Ambas as organizações sincronizam por meio do AAD Conexão, portanto, o AAD agora tem todos os usuários de ambas as implantações locais.
- Todos os usuários abrigados no local.  
- Skype for Business Híbrido *ainda não* está configurado.
- Se os usuários em qualquer implantação usarem Teams, eles não poderão se federar uns com os outros (ou com qualquer organização), nem terão interoperabilidade com Skype for Business usuários. Nesse estágio, a Microsoft recomenda o uso de Teams somente para canais.<br><br>
    ![Figura Um diagrama.](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com é um [domínio](/powershell/module/skype/disable-csonlinesipdomain) SIP online desabilitado. Todos os usuários estão no local. Se eles usarem Teams não têm federação ou interoperabilidade. Nesse estágio, a Microsoft recomenda o uso de Teams somente para canais.
- Skype for Business Híbrido foi habilitado para uma das organizações locais.
- Alguns usuários na organização híbrida foram movidos para a nuvem e estão Teams Somente(usuário A, conforme indicado pelo sombreamento roxo). Esses usuários Teams somente os usuários têm suporte completo de interoperabilidade e federação com qualquer outro Skype for Business usuários.<br><br>
    ![Figura B diagrama.](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Todos os usuários de OriginalCompany. <span> agora estão Teams modo Somente na nuvem. 
- Skype for Business configuração híbrida com a OriginalCompany. <span> a implantação com foi desabilitada. A implantação local foi-se.
- Se AcquiredCompany. <span> com não estava sincronizando anteriormente com o AAD, para continuar a partir daqui, ele precisa ser sincronizado agora. Mas ainda não é híbrido (espaço de endereço SIP compartilhado) e até que a organização esteja pronta para mudar para híbrido, o domínio SIP online para a organização local pura (AcquiredCompany.com) deve permanecer desabilitado, para que os usuários online Teams possam se comunicar com usuários locais.<br><br>
    ![Figura C diagrama.](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> agora está habilitado como um domínio SIP online.
- Local é atualizado para aceitar OriginalCompany. <span> com. (Ambos os domínios permitidos e certificados de borda são atualizados).
- O Espaço de Endereço SIP compartilhado está habilitado entre AcquiredCompany. <span> com e Microsoft 365 organização.
- Alguns usuários na organização híbrida podem ter sido movidos para a nuvem, como o Usuário D abaixo (indicado por sombreamento roxo).<br><br>
    ![Figura D diagrama.](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Outros pontos de partida

As etapas no exemplo canônico acima pressupom que a organização começa com duas implantações federadas no local sem Microsoft 365 presença. No entanto, algumas organizações podem ter uma Microsoft 365 existente e podem haver pontos de entrada diferentes na sequência acima. Há quatro configurações típicas:

- Várias organizações federadas no local sem Microsoft 365 organização. Nesse caso, comece na etapa 1.
- Várias organizações federadas no local que já estão sincronizando várias Skype for Business floresta em um único locatário do Azure AD. Essa organização se parece com a organização hipotética na Figura A, que concluiu as etapas 1-6 e deve começar na etapa 7.
- Uma organização híbrida que federa com 1 ou mais organizações locais puras, nenhuma delas sincronizada com o AAD. Essa organização se pareceria com a organização hipotética **na Figura E**, mostrada abaixo.
    - Essa organização é semelhante à Figura B, que concluiu as etapas 1-9, exceto:
        - Suas implantações de Skype for Business não  híbridas ainda não estão sincronizadas com o Azure AD.
        -  Os domínios SIP online ainda não estão desabilitados. 
    - Essas organizações devem:
        - Conclua a migração da organização híbrida existente e insira a sequência acima na etapa 10.  OR,
        - Se desejar sincronizar quaisquer outras florestas de Skype for Business no AAD antes de concluir a migração da organização híbrida, a organização deverá executar a etapa 7 (desabilitar todos os domínios SIP online em qualquer outra implantação de Skype for Business local que irá sincronizar com o AAD) e habilitar o AAD Conexão e, somente em seguida, continuar com a etapa 10 (desativar a implantação híbrida original).       
                **Figura E**<br>
                ![Figura E diagrama.](../media/cloudconsolidationfige.png)
- Uma organização Teams only que federa com uma organização local Skype for Business local separada. Quando essa organização desabilita o domínio SIP online para a organização local e habilita o AAD Conexão para a organização local do Skype for Business, ela se parece com a organização hipotética mostrada na Figura **[C](#figure-c)** que concluiu as etapas 1-11.

## <a name="limitations"></a>Limitações

- Deve haver no máximo uma organização Microsoft 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
- Somente uma floresta local Skype for Business pode estar no modo híbrido (espaço de endereço SIP compartilhado) por vez. Todas as outras florestas Skype for Business locais devem permanecer puramente locais e devem ser federadas entre si e com a organização Microsoft 365 local.
- Antes de ser migrado para a nuvem, há uma experiência assimétrica para os usuários nesta implantação, pois nem todos os usuários online são representados no local:
    - A experiência pode ser resumida da seguinte forma:
        - Qualquer usuário em casa online interagirá com usuários locais no ambiente híbrido como se o usuário fosse híbrido.
        - Os usuários locais na implantação híbrida interagirão com usuários online representados em seu diretório local como se fossem híbridos. 
        - Os usuários locais na implantação híbrida interagirão com usuários online que não são representados no AD local como federados.
    - Na **[Figura D](#figure-d)** acima, o usuário E está no local em AcquiredCompany. <span> com.  O Usuário E interagirá com o Usuário D (online) usando a experiência híbrida padrão, mas o usuário E terá uma experiência federada com os usuários A, B e C porque eles não são representados no diretório local. No entanto, os usuários A, B e C interagirão com o usuário E como se o usuário estivesse híbrido.
    - Implicações da interação ser híbrida versus federação:
        - A presença não é automaticamente inscrito para usuários federados, a menos que o usuário seja marcado como um contato.
        - O encaminhamento de chamada não funciona entre domínios federados.
        - Os cenários de transferência de chamada são mais limitados.
        - A throttling pode ser aplicada ao tráfego federado.
- Dada essa experiência assimétrica, o suporte oficial para a funcionalidade de chamada em cenários entre locais entre um usuário local e um usuário de nuvem que não está no diretório local está limitado apenas a ponto a ponto. 
    - Não há suporte para encaminhamento de chamada, transferência, filas de chamada etc. entre esses usuários.
    - Esses cenários de chamada sem suporte ainda aparecerão habilitados, mas, em muitos casos, falharão de maneiras imprevisíveis. 
    - Na **[Figura D](#figure-d)** acima, o usuário E está no local e as chamadas com os usuários A, B ou C terão suporte apenas como ponto a ponto. (As chamadas com o usuário D não teriam limitações de suporte.)  No entanto, depois que o usuário local E é movido para a nuvem, essa restrição não se aplica mais.
- Se você tiver mais de uma implantação do Skype for Business Server 2019 em seu ambiente, apenas 1 dessas implantações poderá ser configurada para usar o Atendedor Automático organizacional, já que esse recurso requer Skype for Business Server configuração híbrida. 
- A ordem de algumas das etapas anteriores pode ser ajustada. O principal requisito que deve ser atendido é que, se todos eles são verdadeiros:
    - Mais de uma floresta local Skype for Business sincronização com um único locatário Microsoft 365 locatário no Azure AD.
    - O domínio dividido é habilitado com uma floresta local
    - Pelo menos um usuário na organização híbrida foi migrado para a nuvem<br>   Em seguida, *você deve* desabilitar todos os outros domínios SIP online de qualquer outra floresta local Skype for Business local. Caso contrário, a federação entre usuários online na organização híbrida e usuários locais em outras organizações quebrará em uma direção.

## <a name="implications"></a>Implicações

- Como há limitações no suporte para a funcionalidade de chamada avançada, conforme descrito acima, as organizações devem tratar esses estados assimétricos como transitórios como parte da migração e não persegui-los como estado **estável.**  
- As organizações com várias implantações Skype for Business locais geralmente devem começar com uma implantação que pode ser totalmente migrada para a nuvem, para que a consolidação possa continuar. Entende-se que, em alguns casos, haverá bloqueios de determinados grupos de usuários para os quais ainda não é viável mover para Teams. Quando essa é uma consideração em cenários que envolvem várias florestas Skype for Business, comece a migrar com outra floresta que não tenha essas limitações, se possível.
- Ao mudar do local para a nuvem, os usuários que têm relações de delegação e/ou normalmente estão envolvidos em cenários de encaminhamento de chamada devem ser movidos juntos como uma unidade.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerações sobre como mudar para o modo TeamsOnly

Quando você move os usuários do local para a nuvem em um ambiente híbrido, esses usuários se tornam Teams usuários únicos.

- Ao atribuir o modo TeamsOnly a um usuário, todos os chats e chamadas de qualquer outro usuário chegarão no cliente Teams usuário. 
- Se os usuários com o Skype for Business local usam principalmente o cliente Skype for Business e não Teams, considere a configuração do TeamsUpgradePolicy para que o roteamento para esses usuários locais sempre caiam em Skype for Business em vez de Teams. Para garantir o roteamento adequado de chats e chamadas entre usuários que são o TeamsOnly e usuários que ainda estão usando o Skype for Business local, os usuários locais devem ter um valor efetivo do TeamsUpgradePolicy com um dos modos SfB, em vez de Ilhas (que é o padrão). 
    - Para fazer isso, você deve primeiro definir a instância global do *TeamsUpgradePolicy* do locatário como um destes valores:
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Você pode conceder uma política de todo o locatário usando este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Observação: você deve fazer isso em um nível de locatário, pois a política não pode ser atribuída a usuários individuais que não têm um endereço SIP no diretório online. Embora você tenha desabilitado domínios SIP online para suas implantações locais puras, os usuários nesses domínios não terão endereços SIP no diretório online por design. Portanto, a única maneira de aplicar política a esses usuários locais é atribuindo no nível do locatário. Por outro lado, na implantação híbrida, os usuários terão um endereço SIP no diretório online para que possam receber explicitamente uma política se desejar que eles tenham um valor diferente da política global do locatário.

## <a name="see-also"></a>Confira também

[Atualizar o certificado de borda](cloud-consolidation-edge-certificates.md)

[Atualizar o AAD Connect para incluir mais de uma floresta](cloud-consolidation-aad-connect.md)

[Disabilitar conectividade híbrida para concluir a migração para a nuvem](cloud-consolidation-disabling-hybrid.md)
