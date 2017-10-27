---
title: Habilitar o Microsoft Teams paralelamente ao Skype for Business
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Um guia para usar o Skype for Business e o Microsoft Teams lado a lado.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 760fa47db7965e0c2a74b01ae25f1d23d37d3180
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>Habilitar o Microsoft Teams paralelamente ao Skype for Business 
=============================================================

Para organizações com implantações existentes do Skype for Business Online, a recente introdução do Microsoft Teams representa uma oportunidade de avaliar o potencial do Teams como uma solução única de comunicação e colaboração, um desafio para equilibrar a balança entre as duas soluções e como elas podem coexistir no seu ambiente.

Se o Teams não conseguir atender suas exigências comerciais hoje, você pode começar a adotar o Teams para se tornar a solução única de comunicação e colaboração na sua organização.

O Teams está habilitado por padrão em todos os locatários elegíveis. Portanto, você precisa decidir como gerenciar o Teams lado a lado com o Skype for Business e continuar a atender às expectativas dos usuários.

De forma geral, existem duas grandes jornadas do cliente lado a lado. São elas:

-   **Opção 1:** Jornada do cliente lado a lado não gerenciada.

    A TI não controla ativamente a experiência lado a lado, e os usuários podem decidir pelo aplicativo de sua preferência.

-   **Opção 2:** Jornada do cliente lado a lado gerenciada.

    A TI controla a experiência do lado a lado, levando os usuários por uma jornada de introdução gradual do Teams para primeiro, introduzir um novo espaço de trabalho de colaboração baseado em bate-papo com bate-papo privado, depois experiências de reunião e, por fim, as experiências de chamada do Teams.

![](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>Benefícios e considerações do lado-a-lado
----------------------------------------

Cada uma das jornadas tem benefícios e considerações a serem avaliados para determinar o caminho certo com base no perfil da sua organização. A tabela abaixo mostra a comparação entre as jornadas de cliente lado a lado gerenciadas e não gerenciadas.


<table>
<thead>
<tr class="header">
<th align="left">Caminhos de migração</th>
<th align="left">Lado a lado sem gerenciamento</th>
<th align="left">Lado a lado com gerenciamento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Perfil da organização</strong></td>
<td align="left"><ul>
<li>Normalmente, empresas menores sem recursos exclusivos de TI</li>
<li>A TI permite que o usuário escolha as ferramentas corretas para o seu trabalho a seu exclusivo critério</li>
<li>O uso primário do Skype for Business é IM/P e reuniões</li>
</ul></td>
<td align="left"><ul><li>Normalmente, empresas maiores, de porte médio</li>
<li>A TI deseja controlar mais rigorosamente a distribuição de novas ferramentas</li>
<li>Adoção mais profunda do Skype for Business hoje</li>
<li>Maior complexidade de rede e infraestrutura</li>
<li>Várias localidades</p>
<li>Preferência por um aplicativo único, com recursos exclusivos de UC</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>Benefícios</strong></td>
<td align="left"><ul>
<li>Aproveitar os recursos do Teams que não estão disponíveis no Skype for Business</li>
<li>Local de trabalho moderno e aprimorado no Office 365</li>
<li>Mais flexibilidade para o usuário</li>
<li>Ativação de todos os recursos ao mesmo tempo</li>
</ul></td>
<td align="left"><ul><li>Aproveitar os recursos do Teams que não estão disponíveis no Skype for Business</li>
<li>Local de trabalho moderno e aprimorado no Office 365</li>
<li>Minimizar o impacto de produtividade do usuário</li>
<li>Reduzir a sobreposição de recursos</li>
<li>Racionalizar a escolha da ferramenta para cenários UC</li>
<li>Capacitar TI e a empresa para habilitar recursos conforme for apropriado na organização</li>
<li>Controlar o ritmo de mudança para os usuários</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>Considerações</strong></td>
<td align="left"><ul>
<li>Vários aplicativos com recursos semelhantes que se sobrepõem</li>
<li>Maior probabilidade de confusão para os usuários, o que pode aumentar os chamados de suporte, prejudicar a TI, impactar a produtividade</li>
<li>O planejamento e monitoramento de rede devem levar em consideração o uso de dois serviços</li>
<li>Necessidade de um empenho maior e imediato de gerenciamento de mudanças: conscientização, treinamento e suporte</li>
<li>Os usuários podem se defrontar com limitações de interoperabilidade entre os aplicativos</li>
</ul></td>
<td align="left"><ul><li>A TI tem um controle mais detalhado, desde as licenças até a experiência dos usuários, exigindo ciclos adicionais de planejamento e implementação</li>
<li>Necessidade de formação e ação do usuário para desativar os recursos selecionados no Teams</li>
<li>Necessidade de esforços de gerenciamento mudanças para desativar os recursos selecionados no Teams</li>
<li>O planejamento e monitoramento de rede devem levar em consideração o uso de dois serviços</li>
<li>Os usuários podem se defrontar com limitações de interoperabilidade entre os aplicativos</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>Jornada do cliente lado a lado não gerenciada
---------------------------------------


![](media/guidance_SkypeforBusiness_image4.png)

Em uma jornada do cliente lado a lado não gerenciada, o Teams é introduzido como uma solução de colaboração (espaço de trabalho baseado em bate-papo, canais, aplicativos, integração com outras cargas de trabalho do Office 365, etc.) que envolve software cliente e cliente web em computadores desktop (PC ou Mac) e em dispositivos móveis.


Por padrão, o Teams também apresenta recursos que se sobrepõem com o Skype for Business, como bate-papo e chamadas privadas e reuniões agendadas. Isso significa que o Teams acaba oferecendo comunicação e colaboração completa para a organização, enquanto, ao mesmo tempo, o Skype for Business oferece recursos semelhantes.

O Teams suporta interoperabilidade com os usuários do Skype for Business Online e os usuários terão a oportunidade de escolher o aplicativo de bate-papo e chamada de sua preferência quando o Teams for lançado. Se um usuário escolher o Teams como o aplicativo de sua preferência e outro usuário não tiver instalado o Teams ou tiver escolhido o Skype for Business como o aplicativo de bate-papo e chamada de sua preferência, eles podem continuar conversando e fazendo chamadas entre si através dos recursos de interoperabilidade que fazem parte do Teams.

A Microsoft está aprimorando continuamente as experiências de interoperabilidade. No início, poderá haver alguns casos em que as experiências de interoperabilidade não atendam às expectativas dos usuários. Como o Skype for Business ainda está disponível para os usuários, eles podem mudar para o Skype for Business para os recursos que no momento não podem ser atendidos pelo Teams.

A reuniões agendadas do Teams é outro recurso de sobreposição que permite que os usuários agendem reuniões via Teams ou Skype for Business. Cada um tem suas próprias vantagens e, com o passar do tempo, quando a experiência de reunião do Teams atender aos requisitos da empresa ou superar as funcionalidades das reuniões Skype for Business, é esperado que os usuários troquem naturalmente para reuniões Teams.

Nesta jornada do cliente lado a lado não gerenciada, prepare sua equipe de assistência técnica para lidar com chamados de suporte dos usuários quando estiverem enfrentando problemas com os recursos de interoperabilidade. Ou aconselhe os usuários a escolherem as reuniões Teams em vez de reuniões Skype for Business e vice-versa.

Esta jornada do cliente lado a lado pode ser aplicável à sua organização se os usuários estiverem mais receptivos à natureza da experiência lado a lado sem gerenciamento, e a organização permitir abertamente que os usuários escolham as melhores ferramentas de comunicação e colaboração para atender aos seus requisitos.

<a name="managed-side-by-side-customer-journey"></a>Jornada do cliente lado a lado gerenciada
-------------------------------------

![](media/guidance_SkypeforBusiness_image2.png)

Uma jornada do cliente lado a lado gerenciada começa quando a organização deseja ter mais controle de como o Teams será introduzido.

-   O **primeiro passo** dessa jornada é um piloto limitado do Teams com o escopo em exigências modernas de colaboração (espaço de trabalho baseado em bate-papo, canais, aplicativos, integração com outras cargas de trabalho do Office 365, etc.). As reuniões de canais ad hoc e o bate-papo privado no Teams também estão habilitados para dar uma oportunidade aos usuários pilotos avaliarem a experiência de reuniões Teams e as experiências de bate-papo privado. Os recursos de reuniões agendadas e chamadas privadas do Teams estão desativados nesta fase. Para iniciar um piloto, vá para [Piloto do Teams com o Skype for Business](pilot-essentials.md).
    
-   O **segundo passo** dessa jornada é ampliar a distribuição do Teams para uma colaboração moderna com o bate-papo privado por toda a organização. As reuniões agendadas e as chamadas privadas permanecem desativadas no Teams para reduzir o tempo de sobreposição com os recursos do Skype for Business.

    Nessa fase, talvez seja necessário considerar se o aplicativo de bate-papo de preferência deve ser definido como o do Teams ou do Skype for Business para toda a organização.

    - Se for definido para o Teams, prepare seus usuários para lidar com os primeiros desafios de interoperabilidade quando se comunicarem com outras pessoas dentro de toda a organização.
    
    - Se for definido para o Skype for Business, os bate-papos privados dentro do Teams permanecerão no Teams e os usuários finais poderão tirar proveito imediato da natureza persistente da plataforma cruzada dos recursos de bate-papo do Teams e continuarão a usar o Skype for Business para bate-papos privados no Skype for Business dentro de toda a organização.


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>No momento, a definição do aplicativo de bate-papo de preferência está disponível apenas no nível de cliente. O treinamento de usuários e a campanha de adoção serão necessários para conduzir a configuração pretendida em toda a organização.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

O **terceiro passo** da jornada do cliente lado a lado gerenciada começa quando a organização decidir que os recursos e a experiência de reunião do Teams atende aos requisitos da empresa. Ao habilitar as reuniões privadas e reuniões de canal no Teams, os usuários recebem opções para agendar as reuniões Teams e as reuniões Skype for Business. Portanto, espera-se que, ao longo do tempo, os usuários mudem naturalmente para reuniões Teams, tendo em vista as constantes inovações do Teams. Para ter sucesso ao direcionar o uso do Skype for Business para o Teams, implemente um programa robusto de gerenciamento de mudanças, incluindo treinamentos, suporte e comunicações que expliquem o valor agregado que o Teams oferece aos usuários, com uma orientação clara de como começar com o Teams. Aproveite nossos recursos de [Prontidão do usuário](http://aka.ms/UserReadiness) para ajudar a projetar sua campanha de conscientização.


O **quarto passo** da jornada do cliente lado a lado gerenciada começa com a habilitação de chamadas no Teams. Os recursos de interoperabilidade do Teams serão bem característicos nesta etapa para garantir uma experiência lado a lado descomplicada. De forma ideal, para aplicar o uso do Teams para chamadas privadas, o Teams deve ser definido como o aplicativo de chamada padrão. 

Com o passar do tempo, a organização toda pode utilizar somente o Teams para atender às exigências de comunicação e colaboração, e então partir para o **quinto passo**. Para ver quando novos recursos serão implementados no Teams, consulte o [Mapa do Office 365](http://aka.ms/TeamsRoadmap). 

<a name="managing-side-by-side-experience"></a>Gerenciamento da experiência lado a lado
--------------------------------

Por padrão, o Microsoft Teams está habilitado para organizações com assinaturas elegíveis do Office 365. Se a sua organização se encaixa no perfil para a jornada do cliente lado a lado não gerenciada, recomendamos fortemente que você mantenha tudo como está para promover uma adoção orgânica do Microsoft Teams.

O Teams pode ser acessado por clientes móveis e por clientes desktop de navegador da web modernos que não precisem de privilégios administrativos de TI (para instalação, aplicável atualmente somente ara PC).

Todos os recursos do Teams, de bate-papo e chamada privada, reuniões ad-hoc e agendadas e até mesmo aplicativos estão habilitados por padrão, permitindo que os usuários experimentem e utilizem os recursos que atendam às suas necessidades. A experiência de primeira execução do Teams orienta os usuários a escolher o seu aplicativo de bate-papo e chamada de preferência (Microsoft Teams ou Skype for Business).

Se a sua organização exigir uma liberação mais controlada de novas ferramentas como o Teams, as opções a seguir podem ser consideradas para a sua jornada do cliente lado a lado gerenciada. São elas:

-   Piloto e lançamento do Teams para colaboração. Veja [Piloto do Teams paralelamente ao Skype for Business](pilot-essentials.md).

-   Lançamento do Teams para reuniões

-   Lançamento do Teams para chamadas

### <a name="teams-pilot-and-rollout-for-collaboration"></a>Piloto e lançamento do Teams para colaboração

Na essência, o Microsoft Teams foi construído em torno do bate-papo persistente e da integração com o Office 365 ao aprimorar os Grupos do Office 365.

Uma vez que, por padrão, os usuários da sua organização com uma licença de assinatura elegível do Office 365 estão habilitados para o Teams, um piloto limitado do Teams envolverá desabilitar a licença do Teams para todos os usuários que estejam fora do grupo piloto.

Para focar o lançamento do Teams como uma solução de colaboração e bate-papo privado, além de reduzir a confusão do usuário devido à sobreposição de recursos do Skype for Business, você pode alterar as configurações a seguir do Office 365, em nível de locatário. Para alterar essas configurações do Office 365, consulte [Configurar o Microsoft Teams na sua organização do Office 365](Office-365-set-up.md).

<table>
<thead>
<tr class="header">
<th align="left">Seção</th>
<th align="left">Configuração</th>
<th align="left">Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Chamadas e reuniões</strong></td>
<td align="left"><p>Permitir agendamento de reuniões privadas: <strong>Desativado</strong></p><p>Permitir agendamento de reuniões de canais: <strong>Desativado</strong></p><p>Permitir chamadas privadas: <strong>Desativado</strong></p></td>
<td align="left"><p>Desabilitar essa configuração impede que os usuários agendem reuniões privadas</p><p>Desabilitar essa configuração impede que os usuários agendem reuniões em canais</p><p>Desabilitar essa configuração impede que os usuários façam chamadas privadas (áudio e vídeo)</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Você precisa desabilitar a Chamada Privada dos usuários Business e Enterprise e os usuários Convidados (se o aceso a convidados se aplicar na sua organização).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



Com essa configuração, pode ser apresentado aos usuários podem como as reuniões funcionam no Teams, defendendo o uso de meetup de canais ad-hoc, permitindo o uso de voz, vídeo e compartilhamento de tela como parte da experiência de colaboração moderna. Os usuários finais também podem se beneficiar dos recursos de bate-papo privado persistente em plataforma cruzada do Teams.

Um piloto bem-sucedido do Teams para colaboração e bate-papo privado pode ser acompanhado com uma ampla distribuição através da empresa ao habilitar a licença do Teams para todos os usuários.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left">Durante o piloto, e também na fase dois, quando o bate-papo privado estiver habilitado, um bate-papo entre o usuário do Teams e o usuário do Skype for Business, o usuário não poderá fazer o que segue:<br>
- Iniciar um vídeo a partir de uma sessão de bate-papo<br>
- Transferir arquivos <br>
- Iniciar uma chamada com várias pessoas a partir da sessão de bate-papo<br>
- Os usuários não poderão iniciar uma sessão de compartilhamento de desktop<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>Lançamento do Teams para reuniões

Conforme os usuários forem se acostumando a colaborar usando o Microsoft Teams, as reunião agendadas poderão ser consideradas como o próximo recurso a ser habilitado na organização.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Os organizadores das reuniões agendadas precisam ter suas caixas de correio no Exchange Online multilocatário (ou Exchange Online Dedicated vNext).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

As configurações a seguir podem ser configuradas em nível de locatário para habilitar reuniões agendadas no Teams, e as configurações são aplicáveis somente para usuários Business e Enterprise.

<table>
<thead>
<tr class="header">
<th align="left">Seção</th>
<th align="left">Configuração</th>
<th align="left">Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Chamadas e reuniões</strong></td>
<td align="left"><p>Permitir agendamento de reuniões privadas: <strong>Ativado</strong></p><p>Permitir agendamento de reuniões de canais: <strong>Ativado</strong></p></td>
<td align="left"><p>Habilitar essa configuração permite que os usuários agendem reuniões privadas</p><p>Habilitar essa configuração permite que os usuários agendem reuniões em canais</p></td>
</tr>
</tbody>
</table>


As reuniões agendadas podem ser organizadas através do cliente desktop do Teams, de um navegador ou do Microsoft Outlook, usando o complemento da reunião para o Microsoft Teams. Depois que as reuniões agendadas do Teams estiverem habilitadas, recomendamos que você comece a instruir os usuários para criar novas reuniões no Teams ou atualizar as reuniões Skype for Business existentes para reuniões Teams.

### <a name="rollout-of-teams-for-calling"></a>Lançamento do Teams para chamadas

A chamada privada é o recurso do Teams que será desenvolvido continuamente e, ao longo do tempo, oferecerá uma substituição atraente para o Skype for Business. Quando a sua organização considerar que os recursos de chamadas privadas do Teams atendem aos principais requisitos da empresa, as configurações a seguir podem ser configuradas em nível de locatário para habilitar a chamada privada no Teams. 

<table>
<thead>
<tr class="header">
<th align="left">Seção</th>
<th align="left">Configuração</th>
<th align="left">Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Chamadas e reuniões</strong></td>
<td align="left"><p>Permitir chamadas privadas: <strong>Ativado</strong></p></td>
<td align="left"><p>Habilitar essa configuração permite que os usuários façam chamadas privadas (áudio e vídeo)</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Permitir que os usuários batam papo de forma privada: Habilitar essa configuração permite que os usuários tenham bate-papos privados com outros usuários.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


Nessa fase, todos os usuários devem ser instruídos para escolher o Teams como o aplicativo de chamada de preferência.

Com a habilitação das chamadas privadas, o Teams oferecerá todos os recursos atualmente oferecidos pelo Skype for Business, e os usuários poderão começar a usar o Teams para satisfazer suas necessidades de comunicação e colaboração.


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>Próxima ação:</strong> Depois que o Teams estiver estabelecido e sendo executado lado a lado com o Skype for Business, [Gere valor com a adoção do Teams pelos usuários](continue-journey.md), enquanto continua sua jornada de migração do Skype for Business para o Teams.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>