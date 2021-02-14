---
title: Consolidação na nuvem para o Teams e o Skype for Business
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
localization_priority: Normal
description: Este artigo descreve como obter essa consolidação para organizações com implantações locais do Skype for Business (ou Lync) que estão tentando mover sua carga de trabalho de UC para o Teams e/ou Skype for Business Online.
ms.openlocfilehash: d2733ffacf8b56a5cfe4217553f533950eb82e36
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221485"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidação na nuvem para o Teams e Skype for Business

Muitas grandes empresas têm mais de uma floresta local do AD e, em alguns casos, os clientes têm mais de uma implantação do Exchange e/ou do Skype for Business Server (ou do Lync Server). Além disso, até mesmo as organizações com apenas uma floresta local podem se encontrar em uma situação semelhante no caso de fusões ou aquisições empresariais. À medida que esses clientes se movem para a nuvem, eles querem consolidar as várias instâncias de uma determinada carga de trabalho local na nuvem em uma única organização do Microsoft 365 ou Office 365. Este artigo descreve como obter essa consolidação para organizações com várias implantações locais do Skype for Business (ou Lync) que querem mover sua carga de trabalho de UC para a nuvem da Microsoft, por exemplo, o Microsoft Teams e/ou o Skype for Business Online.

Historicamente, a orientação era a de que clientes nessa situação deviam consolidar as implantações no local primeiro e depois migrar para a nuvem. Embora essa ainda seja uma opção, este artigo descreve uma solução baseada em novas funcionalidades que permitem que organizações com várias implantações do Skype for Business migrem uma implantação por vez para uma única organização do Microsoft 365 ou Office 365, sem fazer consolidação local. Observe que, mesmo com essa nova funcionalidade, o Skype for Business Online e o Microsoft Teams não suportam várias florestas do Skype for Business/Lync no modo híbrido com uma única organização do Microsoft 365 ou Office 365. 

> [!Important]
> Antes de usar este guia para configuração, revise e compreenda [as](#limitations)Limitações, pois elas podem afetar sua organização.

## <a name="overview-of-cloud-consolidation"></a>Visão geral da consolidação na nuvem

A consolidação de todos os usuários locais na nuvem em uma única organização do Microsoft 365 ou office 365 pode ser alcançada para qualquer organização com várias implantações do Skype for Business, desde que os seguintes requisitos principais sejam atendidos:

- Deve haver no máximo uma organização do Microsoft 365 ou Office 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
- Em qualquer momento, somente uma floresta do Skype for Business local pode estar no modo híbrido (Espaço de Endereçamento SIP Compartilhado). Todas as outras florestas locais do Skype for Business devem permanecer no local (e supostamente federadas umas com as outras). Observe que essas outras organizações locais podem sincronizar com o AAD se desejarem com novas funcionalidades para desabilitar os [domínios SIP online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponíveis a partir de dezembro de 2018. 

Os clientes com implantações do Skype for Business em várias florestas devem migrar totalmente todos os usuários de uma única floresta híbrida do Skype for Business individualmente para a organização do Microsoft 365 ou Office 365 usando a funcionalidade Espaço de Endereço SIP Compartilhado e, em seguida, desabilitar a implantação híbrida com essa implantação local antes de migrar a próxima implantação local do Skype for Business. Antes de serem migrados para a nuvem, os usuários locais permanecem em um estado federado com todos os usuários que não são representados no diretório local do mesmo usuário.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemplo canônico de consolidação na nuvem

Considere uma organização com duas implantações locais federadas separadas do Skype for Business que deseja consolide-las online no Microsoft Teams ou no Skype for Business Online.


|Detalhes do estado original |Detalhes de estado desejados |
|---------|---------|
|<ul><li>2 implantações locais independentes do Skype for Business em florestas separadas do AD<li>No máximo 1 floresta está híbrida com o Skype for Business Online <li> As organizações são federadas entre si <li>Os usuários não são sincronizados entre essas florestas<li> A organização pode ter uma organização do Microsoft 365 ou Office 365 e pode estar sincronizando seu diretório no Azure AD</ul>|<ul> <li>1 Organização do Microsoft 365 ou Office 365<li>Não há mais implantações locais, portanto, não há mais implantações híbridas restantes<li>Todos os usuários locais estão no Skype for Business Online e, opcionalmente, podem ser usuários somente do Teams <li>Nenhuma área local do Skype for Business em qualquer lugar <li>Os usuários ainda têm autenticação local</ul> |

![Consolidando duas implantações locais federadas separadas](../media/cloudconsolidationfig1.png)  

As etapas básicas para obter do estado original para o estado final desejado estão abaixo.  Observe que algumas organizações podem descobrir que seu ponto de partida está em algum lugar no meio dessas etapas. Consulte [Outros pontos de partida,](#other-starting-points)mais adiante neste artigo. Por fim, em alguns casos, a ordem pode ser ajustada, dependendo da necessidade. [Restrições e limitações principais são descritas](#limitations) posteriormente.

1.  Obter uma organização do Microsoft 365 ou Office 365 se ainda não existir.
2.  Certifique-se de que todos os domínios SIP relevantes em ambas as implantações locais sejam verificados nos domínios do Microsoft 365 ou Office 365.
3.  Escolha uma implantação do Skype for Business que será híbrida com o Microsoft 365 ou o Office 365. Neste exemplo, vamos usar OriginalCompany. <span> com.
4.  [Habilita o AAD Connect para a floresta](configure-azure-ad-connect.md) que se tornará híbrida (OriginalCompany. <span> com). 
5.  Se você for introduzir o Teams em sua organização, de definir a política para todo o locatário do [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) como SfBWithTeamsCollab ou um dos outros modos SfB (SfBOnly ou SfBWithTeamsCollabAndMeetings). Isso é fundamental para garantir o roteamento de chamadas e chats de usuários que se movem para o Teams Apenas para usuários que permanecem no local.
6.  É recomendável neste ponto (mas ainda não é necessário até a etapa 11) habilitar o [AAD Connect](cloud-consolidation-aad-connect.md) para a outra floresta (AcquiredCompany. <span> com). Supondo que o AAD Connect seja habilitado em ambas as florestas, a organização se parece com a Figura **[A,](#figure-a)** que pode ser um ponto de partida comum para algumas organizações. 
7.  Para quaisquer domínios SIP hospedados por outras implantações locais (neste caso, AcquiredCompany. <span> com), [desabilite esses domínios SIP no Skype for Business Online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) usando o `Disable-CsOnlineSipDomain` PowerShell. (Essa é uma nova funcionalidade a partir de dezembro de 2018.)
8.  [Configurar o Skype for Business híbrido](configure-federation-with-skype-for-business-online.md) para OriginalCompany. <span> com (a única implantação que ainda habilitar domínios SIP online).
9.  Na implantação híbrida (OriginalCompany. <span> com), comece a mover os usuários do [Skype for Business](move-users-between-on-premises-and-cloud.md) local para a nuvem (seja o Teams Apenas ou não) para que essa conta seja homed no Skype for Business Online. Agora a organização se parece com **[a Figura B.](#figure-b)** As principais alterações da Figura A são:
    - Os usuários de ambos os diretórios locais agora estão no AAD.
    - AcquiredCompany. <span> com é um domínio SIP online desabilitado.
    - Alguns usuários foram movidos online para o Skype for Business Online ou o Teams. (Consulte o usuário roxo A.)
10. Depois que todos os usuários são movidos para a nuvem, [desabilite](cloud-consolidation-disabling-hybrid.md) a implantação híbrida com o Skype for Business local para OriginalCompany. <span> com do Office 365:  
    - Desabilite o domínio dividido na organização do Microsoft 365 ou Office 365.
    - Desabilite a capacidade de se comunicar com o Microsoft 365 ou o Office 365 na OriginalCompany. <span> com no local.
    - Atualize registros DNS para OriginalCompany. <span> para apontar para o Microsoft 365 ou Office 365.
11. Se ainda não tiver feito isso, [habilita o AAD Connect para a](cloud-consolidation-aad-connect.md) próxima floresta que ficará híbrida (AcquiredCompany. <span> com). Neste ponto, a organização se parece com **[a Figura C.](#figure-c)** Esse pode ser outro ponto de partida comum para algumas organizações. 
12. No PowerShell, [habilita](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain) os domínios SIP para a próxima implantação local que será híbrida, AcquiredCompany. <span> com. Isso é feito usando a nova funcionalidade disponível a partir `Enable-CsOnlineSipDomain` de dezembro de 2018.
13. Se você estiver usando federação fechada, deverá adicionar qualquer domínio SIP (excluindo .microsoftonline.com) do locatário online puro como Domínios Permitidos no mesmo \* Microsoft 365 ou Office 365.  Observe que pode levar algum tempo até que a alteração entre em vigor e não há problema em fazer isso antecipadamente, portanto, sugerimos fazer isso bem antes de passar para a etapa 14.
14. Atualize o ambiente local para aceitar qualquer domínio SIP do locatário online, para que eles se matchm.
    - [Atualize](cloud-consolidation-edge-certificates.md) o SAN em todos os certificados de borda para ter o mesmo valor de antes, mais valores para qualquer domínio SIP online existente (exceto *.microsoftonline.com), neste caso, Sip.OriginalCompany. <span> com.
    - Certifique-se de OriginalCompany. <span> com é um [domínio permitido](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) na implantação local, AcquiredCompany. Adicionar domínios permitidos.
15. [Habilitar o Skype for Business](configure-federation-with-skype-for-business-online.md) híbrido entre AcquiredCompany local. <span> com e a nuvem.
16. Conforme desejado, [migre os usuários do local para a nuvem.](move-users-between-on-premises-and-cloud.md) Você pode migrar os usuários diretamente para o [modo TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) ou pode migrá-los primeiro para o Skype for Business Online. Durante esse estado, a organização se parece com **[a Figura D.](#figure-d)**
17. Depois que todos os usuários são migrados, desabilite a configuração [híbrida](cloud-consolidation-disabling-hybrid.md) com o ambiente local para *tornar a organização pura nuvem!*

Os diagramas abaixo mostram a configuração em vários pontos-chave durante esse processo.

##### <a name="figure-a"></a>Figura A:

- Ambas as organizações sincronizam por meio do AAD Connect, portanto, o AAD agora tem todos os usuários de ambas as implantações locais.
- Todos os usuários que estão no local.  
- O Skype for Business Híbrido *ainda não* está configurado.
- Se os usuários em qualquer uma das implantações usarem o Teams, eles não poderão federar uns com os outros (ou com qualquer organização) nem terão interoperabilidade com os usuários do Skype for Business. Neste estágio, a Microsoft recomenda o uso do Teams somente para Canais.<br><br>
    ![Figura A diagrama](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figura B:

- AcquiredCompany. <span> com é um [domínio](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) SIP online desabilitado. Todos os usuários são locais. Se eles usarem o Teams, eles não terão federação ou interoperabilidade. Neste estágio, a Microsoft recomenda o uso do Teams somente para Canais.
- O Skype for Business Híbrido foi habilitado para uma das organizações locais.
- Alguns usuários na organização híbrida foram movidos para a nuvem (usuário A, conforme indicado pelo sombreamento roxo). Esses usuários podem ser usuários do Skype for Business Online ou do Teams Only com total interoperabilidade e suporte à federação.<br><br>
    ![Figura B diagrama](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figura C:

- Todos os usuários da OriginalCompany. <span> agora estão na nuvem (no Skype for Business Online). É recomendável que eles também sejam Apenas Teams.
- Configuração híbrida do Skype for Business com a OriginalCompany. <span> a implantação com foi desabilitada. A implantação local foi-se.
- Se AcquiredCompany. <span> com não estava sincronizando anteriormente com o AAD, para continuar a partir daqui ele precisa ser sincronizado agora. Mas ainda não é híbrido (espaço de endereço SIP compartilhado) e até que a organização esteja pronta para mudar para a híbrida, o domínio SIP online para a organização pura local (AcquiredCompany.com) deve permanecer desabilitado, para que os usuários online do Teams possam se comunicar com usuários locais.<br><br>
    ![Figura C diagrama](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figura D:

- AcquiredCompany. <span> com agora está habilitado como um domínio SIP online.
- O local é atualizado para aceitar OriginalCompany. <span> com. (Os certificados de domínio permitido e de borda são atualizados).
- O Espaço de Endereço SIP Compartilhado é habilitado entre AcquiredCompany. <span> com e organização do Microsoft 365 ou Office 365.
- Alguns usuários na organização híbrida podem ter sido movidos para a nuvem, como o Usuário D abaixo (indicado pelo sombreamento roxo).<br><br>
    ![Figura D diagrama](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Outros pontos de partida

As etapas no exemplo canônico acima pressupom que a organização começa com duas implantações locais federadas sem presença da Microsoft ou do Office 365. No entanto, algumas organizações podem ter uma área existente do Microsoft 365 ou Office 365, e pode haver pontos de entrada diferentes na sequência acima. Há quatro configurações típicas:

- Várias organizações locais federadas sem nenhuma organização do Microsoft 365 ou Office 365. Nesse caso, comece na etapa 1.
- Várias organizações locais federadas que já estão sincronizando várias florestas do Skype for Business em um único locatário do Azure AD. Essa organização se parece com a organização hipotética na Figura A, que concluiu as etapas de 1 a 6 e deve começar na etapa 7.
- Uma organização híbrida que federa uma ou mais organizações locais puras, nenhuma delas sincronizada com o AAD. Essa organização se pareceria com a organização hipotética **na Figura E,** mostrada abaixo.
    - Essa organização é semelhante à Figura B, que concluiu as etapas de 1 a 9, exceto:
        - Suas implantações não híbridas do Skype for Business *AINDA NÃO* estão sincronizadas com o Azure AD.
        -  Os domínios SIP online ainda não estão desabilitados. 
    - Essas organizações devem:
        - Conclua a migração da organização híbrida existente e insira a sequência acima na etapa 10.  OU,
        - Se desejar sincronizar outras florestas do Skype for Business no AAD antes de concluir a migração da organização híbrida, a organização deve executar a etapa 7 (desabilitar todos os domínios SIP online em qualquer outra implantação local do Skype for Business que será sincronizada no AAD) e habilitar o AAD Connect e, em seguida, continuar somente na etapa 10 (encerrar a implantação híbrida original).       
                **Figura E**<br>
                ![Figura E diagrama](../media/cloudconsolidationfige.png)
- Uma organização pura do Skype for Business Online (que pode ou não estar usando o Teams) que federa com uma organização local separada do Skype for Business. Depois que essa organização desabilita o domínio SIP online para a organização local e habilita o AAD Connect para a organização local do Skype for Business, ela se parece com a organização hipotética mostrada na Figura **[C](#figure-c)** que concluiu as etapas 1 a 11.

## <a name="limitations"></a>Limitações

- Deve haver no máximo uma organização do Microsoft 365 ou Office 365 envolvida. Não há suporte para consolidação em cenários com mais de uma organização.
- Apenas uma floresta local do Skype for Business pode estar no modo híbrido (espaço de endereço SIP compartilhado) por vez. Todas as outras florestas locais do Skype for Business devem permanecer puramente locais e devem ser federadas entre si e com a organização do Microsoft 365 ou office 365.
- Antes de migrar para a nuvem, há uma experiência assimétrica para os usuários nesta implantação, porque nem todos os usuários online são representados no local:
    - A experiência pode ser resumida da seguinte forma:
        - Qualquer usuário que estiver online interagirá com usuários locais no ambiente híbrido como se o usuário fosse híbrido.
        - Os usuários locais na implantação híbrida interagirão com usuários online representados em seu diretório local como se fossem híbridos. 
        - Os usuários locais na implantação híbrida interagirão com usuários online que não são representados no AD local como federados.
    - Na **[Figura D](#figure-d)** acima, o usuário E está no local em AcquiredCompany. <span> com.  O Usuário E interagirá com o Usuário D (online) usando a experiência híbrida padrão, mas o usuário E terá uma experiência federada com os usuários A, B e C porque eles não são representados no diretório local. No entanto, os usuários A, B e C interagirão com o usuário E como se o usuário estivesse no híbrido.
    - Implicações da interação ser híbrida versus federação:
        - A presença não é automaticamente inscreve-se para usuários federados, a menos que o usuário seja marcado como um contato.
        - O encaminhamento de chamada não funciona entre domínios federados.
        - Os cenários de transferência de chamada são mais limitados.
        - A throttling pode ser aplicada ao tráfego federado.
- Devido a essa experiência assimétrica, o suporte oficial para a funcionalidade de chamada em cenários entre locais entre um usuário local e um usuário na nuvem que não está no diretório local é limitado a apenas ponto a ponto. 
    - Não há suporte para encaminhamento de chamada, transferência, filas de chamada etc. entre esses usuários.
    - Esses cenários de chamada sem suporte ainda aparecerão habilitados, mas, em muitos casos, falharão de maneiras imprevisíveis. 
    - Na **[Figura D](#figure-d)** acima, o usuário E está no local e as chamadas com os usuários A, B ou C serão suportadas apenas como ponto a ponto. (Chamadas com o usuário D não teriam limitações de suporte.)  No entanto, depois que o usuário E local é movido para a nuvem, essa restrição não se aplica mais.
- Se você tiver mais de uma implantação do Skype for Business Server 2019 em seu ambiente, apenas 1 dessas implantações poderá ser configurada para usar o Atendente Automático Organizacional, já que esse recurso requer a configuração híbrida do Skype for Business Server. 
- A ordem de algumas das etapas anteriores pode ser ajustada. O principal requisito que deve ser atendido é que, se todos eles são verdadeiros:
    - Mais de uma floresta local do Skype for Business sincronizando com um único locatário do AAD
    - O domínio dividido é habilitado com uma floresta local
    - Pelo menos um usuário na organização híbrida foi migrado para a nuvem<br>   Em seguida, *você deve* desabilitar todos os outros domínios SIP online de qualquer outra floresta local do Skype for Business. Caso contrário, a federação entre usuários online na organização híbrida e os usuários locais em outras organizações será desabrida em uma direção.

## <a name="implications"></a>Implicações

- Como há limitações no suporte para a funcionalidade de chamada avançada conforme descrito acima, as organizações devem tratar esses estados assimétricos como parte da migração e não os buscar como um estado **estável.**  
- As organizações com várias implantações locais do Skype for Business geralmente devem começar com uma implantação que pode ser totalmente migrada para a nuvem, para que a consolidação possa continuar. É entendido que, em alguns casos, haverá bloqueios de determinados grupos de usuários para os quais ainda não é viável mudar para o Teams. Quando essa for uma consideração em cenários que envolvem várias florestas do Skype for Business, comece a migrar com outra floresta que não tenha essas limitações, se possível.
- Ao mudar do local para a nuvem, os usuários que têm relações de delegação e/ou normalmente estão envolvidos em cenários de encaminhamento de chamada devem ser movidos juntos como uma unidade.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considerações para mudar para o modo TeamsOnly

Ao mover usuários do local para a nuvem em um ambiente híbrido, você pode movê-los para o modo Somente Skype for Business ou TeamsOnly. *Se você planeja mover os usuários para o modo TeamsOnly, leia esta seção primeiro.*

- Quando você atribui o modo TeamsOnly a um usuário, todos os chats e chamadas de qualquer outro usuário chegarão ao cliente do Teams desse usuário. 
- Se os usuários com o Skype for Business local usam principalmente o cliente Skype for Business e não o Teams, considere a configuração do TeamsUpgradePolicy para que o roteamento para esses usuários locais sempre chega ao Skype for Business em vez do Teams. Para garantir o roteamento adequado de chats e chamadas entre usuários que são TeamsOnly e usuários que ainda estão usando o Skype for Business no local, os usuários locais devem ter um valor efetivo de TeamsUpgradePolicy com um dos modos SfB, em vez de Ilhas (que é o padrão). 
    - Para fazer isso, você deve primeiro definir a instância global do *TeamsUpgradePolicy* do locatário como um destes valores:
        - SfBWithTeamsCollab (recomendado)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Você pode conceder uma política em todo o locatário usando este comando:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Observação: você deve fazer isso em nível de locatário porque a política não pode ser atribuída a usuários individuais que não têm um endereço SIP no diretório online. Embora você tenha desabilitado domínios SIP online para suas implantações locais puras, os usuários nesses domínios não terão endereços SIP no diretório online por design. Portanto, a única maneira de aplicar a política a esses usuários locais é atribuindo no nível do locatário. Por outro lado, na implantação híbrida, os usuários terão um endereço SIP no diretório online para que possam receber explicitamente uma política se desejar que tenham um valor diferente da política global do locatário.
- A UX do cliente do Teams ainda não está de acordo com os modos SfB do TeamsUpgradePolicy. Por exemplo, quando nesses modos, a iniciação de chamada e chat no Teams é possível no momento, embora no futuro esse não seja o caso. Isso pode causar confusão entre os usuários porque às vezes as respostas podem chegar ao Teams e, às vezes, ao Skype for Business, dependendo das circunstâncias. É recomendável que você desabilite separadamente a chamada e o chat via TeamsMessagingPolicy e TeamsCallingPolicy para usuários que ainda estão no local.

## <a name="see-also"></a>Confira também

[Atualizar o certificado de borda](cloud-consolidation-edge-certificates.md)

[Atualizar o AAD Connect para incluir mais de uma floresta](cloud-consolidation-aad-connect.md)

[Disabilitar conectividade híbrida para concluir a migração para a nuvem](cloud-consolidation-disabling-hybrid.md)
