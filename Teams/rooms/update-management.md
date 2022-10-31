---
title: Gerenciamento de atualizações de gerenciamento de Salas Microsoft Teams Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: monitoramento proativo de suas salas de reunião.
f1keywords: ''
ms.openlocfilehash: 285f0bd9862dc5d4c490587e574aa53e4869df80
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792870"
---
# <a name="update-management"></a>Gerenciamento de atualizações 
Uma sala de reunião moderna é equipada com um dispositivo Salas do Microsoft Teams e outros periféricos, como câmera, microfone ou alto-falante, e potencialmente mais dispositivos para criar uma experiência de reunião inclusiva e eficaz. Equipamentos de diferentes tipos de OEMs fornecem a experiência organizacional exata desejada; no entanto, eles devem ser mantidos com software e firmware em uma base contínua.  

Salas Microsoft Teams Pro Management fornece a garantia de que cada sala em sua organização será mantida em níveis recomendados para entregar uma sala sempre pronta e funciona corretamente. O objetivo da Microsoft é reduzir a complexidade e o trabalho em conjunto para sua equipe operacional com inteligência e automação. A solução de problemas ou diagnósticos é executada o mais rápido possível. 

## <a name="transitioning-a-device-to-pro-management"></a>Transição de um dispositivo para o Pro Management 
Os dispositivos de sala integrados ao Pro Management geralmente têm um histórico e uma prática de gerenciamento de alterações diferentes de nossas diretrizes.  

- Para se beneficiar do Pro Management, você deve fazer a transição do gerenciamento de alterações para todas as atualizações no portfólio do Pro Management.
- Várias fontes de SLAs de incidentes de impacto de gerenciamento de alterações, pois há uma descoberta e correção que será reiniciada novamente se um incidente acontecer na sala.
- A Microsoft implementou controles e verificações para implementar políticas que podem ser diferentes de uma organização para outra e a capacidade de intervir em situações excepcionais.
- Eventualmente, os dispositivos de sala serão atualizados para padrões comuns, exceto para exceções devido a problemas com uma instalação de hardware específica.  

## <a name="transitioning-devices-basic-readiness-checks"></a>Dispositivos de transição: verificações básicas de preparação 
A maioria das falhas inesperadas surgem de alterações na imagem base com histórico incerto de gerenciamento de alterações. 

Recomenda-se seguir verificações de preparação simples:  

- **Imagem base**: a imagem base deve ser do OEM específico. Se o dispositivo tiver sido reconstruído no passado e mostrar falhas ou comportamentos inesperados em tarefas comuns, a imagem base deverá ser restaurada. Podemos fornecer assistência, mas não podemos recompilar remotamente o dispositivo de sala, portanto, você precisará de um técnico local do site.  
- **Sistema operacional base, edição:** O sistema operacional base e a edição devem corresponder aos requisitos de dispositivos Salas do Microsoft Teams. Se isso não for assim, ele deve ser corrigido como parte da integração. Salas do Microsoft Teams requer as SKUs Windows 10 IoT Enterprise ou Windows 10 Enterprise em Semi-Annual Opções de manutenção do Canal. Consulte as [diretrizes oficiais do MTR](rooms-lifecycle-support.md#windows-10-release-support) para obter mais informações.

## <a name="readiness-checks"></a>Verificações de preparação

Há alguns pré-requisitos para receber atualizações por meio do serviço de Gerenciamento Profissional: 

|Software |Orientação |
|:- |:- |
|Logitech Sync Services  |Deve ser instalado e em execução nos dispositivos da sala de reunião do Logitech. Os serviços de sincronização necessários serão instalados automaticamente do Windows Atualizações, a menos que sejam bloqueados. O pacote sincronização completo também pode ser instalado. |
|Atualizações do sistema operacional Windows |Deve ser mantido habilitado e não redirecionado para o WSUS nem bloqueado de uma perspectiva de rede. Nem as políticas de GPO nem MDM devem ser usadas para gerenciar atualizações do sistema operacional. |
|Atualizações da Microsoft Store   |Deve ser desligado. Os Serviços Gerenciados desativarão as atualizações da Loja se forem encontradas. |
|Software Antivírus |Se você estiver executando o software AV nesses dispositivos, verifique se o AV tem exclusões em vigor para as dlls do Teams e do Skype. Consulte [Como incluir ou excluir o Teams de aplicativos antivírus ou DLP](/microsoftteams/troubleshoot/teams-administration/include-exclude-teams-from-antivirus-dlp) para obter mais detalhes. |
|Software Adicional |Software adicional, como exibição de área de trabalho remota de terceiros, etc. deve ser revisado com serviços gerenciados para excluir efeitos colaterais. |
|Gerenciamento adicional de alterações|Pode interferir nas atualizações cobertas e não deve ser introduzido. |

## <a name="managed-updates--how-it-works"></a>Atualizações gerenciadas – Como funciona 
Há duas maneiras primárias de como as atualizações são gerenciadas:  

- **Gerenciado automaticamente**: Atualizações são instalados no dispositivo de sala com base na avaliação do Pro Management. Nenhuma intervenção é necessária para as atualizações gerenciadas em nosso portfólio.
- **Anel validado**: configure um sistema de anel para visualizar atualizações em dispositivos específicos para que você possa monitorá-las sem o trabalho de perna associado. A instalação do anel fornece uma camada adicional de due diligence antes de distribuições amplas.  

### <a name="automatically-managed"></a>Gerenciado automaticamente

Se você optar por ser gerenciado automaticamente, nenhuma ação será necessária para as atualizações de sua parte. No entanto, você deve examinar o portfólio atual de atualizações com suporte pelo serviço de Gerenciamento Profissional. O portfólio está constantemente recebendo novas adições e é nossa prioridade cobrir as atualizações mais frequentes e impactantes para garantir a estabilidade do quarto. Verifique a lista atual (na seção "Gerenciamento de Atualizações" deste documento) para planejar qualquer gerenciamento de alterações adicional necessário para sua organização.  

**Recomendação:** Não instale atualizações cobertas pelo serviço pro management em qualquer dispositivo gerenciado por conta própria. 

### <a name="ring-validation"></a>Validação de anel

Ao escolher a validação do anel, examine as seções a seguir sobre como os anéis funcionam no portal de Gerenciamento de Profissionais e as opções disponíveis para personalizá-lo para sua organização. Mesmo com a validação do anel, são feitas tentativas para garantir que as salas não sejam passadas devido às atualizações recomendadas. Dependendo da situação, uma sala pode receber atualizações de "recuperar o atraso" para garantir que ela esteja em conformidade com as recomendações da Microsoft.  

 Verifique se há anúncios na home page do portal e na documentação do Pro Management à medida que novos tipos de software e firmware se tornam disponíveis no portfólio. 

### <a name="scheduling"></a>Agendar 
Atualizações são agendados para salas com base no equipamento na sala e se não estiverem atendendo aos padrões recomendados para software e firmware aplicáveis. 

- Para ajudar nossos clientes a atender aos requisitos de gerenciamento de alterações, atualize o início da implantação às **quartas-feiras** no anel de preparo. Se uma atualização crítica for necessária, essa agenda será ignorada e a atualização lançada assim que estiver disponível. 
- Atualizações são sequenciados com base na necessidade em uma sala específica. 
- Se você tiver anéis de instalação para validar as atualizações, a atualização avançará por meio da ordem do anel. 
- Uma nova atualização pode substituir uma atualização que está enfileirada se for determinado que a estabilidade do quarto melhorará, com base em sua situação.  
- Atualizações normalmente são aplicadas durante nossa janela de manutenção noturna – que é o horário local **das 12h às 5h** para evitar qualquer tipo de interrupção. 

## <a name="microsoft-teams-rooms-app-update-lifecycle-policy"></a>Salas do Microsoft Teams política de ciclo de vida de atualização de aplicativo 
A política de suporte da equipe de engenharia mtr afirma que todo o suporte termina após o ciclo de vida de doze (12) meses para uma versão ter expirado ou se mais de duas atualizações foram lançadas desde então. Em seguida, os clientes devem atualizar para uma versão com suporte. Referencie [Salas do Microsoft Teams suporte à versão do aplicativo – Microsoft Teams | Microsoft Docs](rooms-lifecycle-support.md) para descrição detalhada do serviço. 

## <a name="update-management-experience-walk-through"></a>Passo a passo da experiência de Gerenciamento de Atualizações  
Para exibir atualizações, faça logon no portal do Pro Management e navegue até a página Atualizações.

O painel Atualizações exibe uma visão geral de alto nível do gerenciamento de atualizações para suas salas com as seguintes guias:

- **Atualizações**: atualizações de software ou firmware aplicáveis à sua organização.  
- **Salas**: a guia Salas fornece uma exibição de salas e anéis aos quais cada sala pertence.
- **Anéis**: a guia Anéis mostra os anéis de salas para sua organização.

### <a name="updates"></a>Atualizações  

Essa exibição mostra as atualizações relevantes para seu locatário e seu respectivo status. Para exibir atualizações passadas que não estão mais ativas, selecione **a alternância Incluir atualizações passadas** para ON.  

Qualquer atualização pode estar em um dos seguintes estados:

| Status | Descrição |
|:- |:- |
| Agendada | Uma atualização está agendada para as salas em um determinado anel. Lembre-se de que uma atualização só mostrará Agendado depois que a progressão atingir o anel em que a sala está. Por exemplo, se uma nova atualização estiver no anel Preparo, ela só mostrará Agendado para salas no anel Preparo.<br></br><p> Outros anéis terão um status "Não necessário" até que a atualização progrida para esse anel.</p> |
| Em andamento | Uma atualização está em andamento e anéis individuais mostram status. Esse estado mostra o status geral do anel e, portanto, se uma atualização se aplicar a uma única sala no anel Preparo em seu locatário, a atualização terá um estado "Em Andamento" até que o anel do Executivo seja atingido. |
| Concluído com falhas | Uma atualização concluiu a progressão por meio de todos os anéis configurados e falhou em pelo menos uma sala. |
| Concluído | Uma atualização concluiu a progressão por meio de todos os anéis configurados e foi instalada com êxito em todas as salas aplicáveis.|
| Preterido | Uma atualização foi desativada. A implantação adicional é interrompida. Isso é típico porque a atualização foi substituída por uma nova versão. |
| Pausado | Uma atualização está em um estado pausado. |
| Não obrigatório | A atualização ainda não foi avaliada para a sala ou não se aplica à sala. |

### <a name="rooms"></a>Quartos  

A guia Salas mostra todas as salas em seu locatário e a qual anel elas pertencem.  

![Captura de tela de todos os anéis de locatário e seus quartos](../media/update-management-002.jpg)

Para configurar a qual anel um quarto deve pertencer:  

1. Clique na sala para criar a exibição detalhada.  
1. Em **Anel**, clique em **Alterar**.  
1. Selecione o Anel ao qual a sala deve pertencer.  
1. Clique **em Atribuir**.  

A exibição detalhada da sala exibe as atualizações relevantes e seu status no **nó Atualizações**.  

![Captura de tela de atualizações e alterações relevantes](../media/update-management-003.jpg)

### <a name="rings"></a>Anéis  

Os anéis são usados para reduzir o risco de problemas derivados da implantação das atualizações de recurso. Isso é feito implantando gradualmente a atualização em todo o site. Cada anel deve ter uma lista de salas do Microsoft Teams Room e uma agenda de distribuição correspondente. Definir anéis geralmente é um evento único (ou pelo menos pouco frequente), mas a TI deve revisitar esses grupos de tempos em tempos para garantir que o sequenciamento ainda esteja correto.  

A guia **Anéis** lista todos os anéis em seu locatário. Há três anéis pré-configurados:  

- **Preparo**: atribua salas ao anel Preparo, que é o seu testbed. Todas as novas atualizações serão lançadas aqui primeiro. Geralmente, você deseja garantir que seu anel de preparo represente salas com a diversidade de tipos de dispositivo em seu ambiente. Se houver certos tipos de salas com uma configuração incomum ou um histórico de problemas de exibição, considere representá-los no Preparo.

- **Geral**: por padrão, todas as salas são colocadas neste anel. A maioria dos dispositivos de sala que estão sendo usados em toda a empresa se enquadra nessa categoria. 

- **Executivo**: esse grupo deve incluir as salas mais importantes em que você deseja minimizar a interrupção proativamente. Um bom exemplo é uma grande sala de conferência usada para reuniões executivas ou grandes reuniões de equipe. 

### <a name="specifying-rollout-timeline"></a>Especificando a linha do tempo de distribuição

Atualizações não pode exceder 60 dias para ser concluída em todos os anéis.  

|Parâmetro |Explicação |
|:- |:- |
|Período de adiamento|Depois que uma atualização começa com o primeiro anel, o período de adiamento é o atraso em dias antes de a atualização ser iniciada neste anel.|
|Duração da distribuição|<p>Depois que a atualização começa neste anel, este é o momento de implantar neste anel. Por exemplo, se a duração for de 5 dias, ela será implantada ao longo de 5 dias nas salas neste anel quando a atualização for iniciada neste anel.|
|Período de teste|O número de dias para testar/validar a atualização em um anel uma vez aplicado ao anel. O período de teste começa depois que a distribuição é concluída e, uma vez concluída, a atualização passa para o próximo anel.|
|Tempo de conclusão|A coluna "Tempo de conclusão" indica o número total de dias (duração de distribuição + período de teste) para que esse anel seja concluído.|
|Tempo Total|Na parte inferior está a linha "Total" que indica quanto tempo uma atualização levará para ser concluída do primeiro ao último anel.|

### <a name="creating-custom-rings"></a>Criando anéis personalizados

1. Navegue até a guia **Anéis** .  
1. Clique **em Adicionar anel**.  
1. Especifique a ordem na qual esse anel receberá a atualização, onde 1 é o primeiro e 9 é o último.  
1. Dê um nome a esse anel.  
1. Forneça uma descrição, se desejar.  
1. Especifique o número de dias que a atualização será distribuída neste anel.  
1. Especifique o período de teste.  
1. Clique **em Enviar**.  

> [!NOTE]
> O "Dias definidos por outros anéis" é o número total de dias que uma atualização levará para ser concluída em todos os anéis. Os "dias restantes" indicam os dias máximos para *que esse* anel seja concluído. A soma de "Duração de distribuição em dias" e "Período de teste em dias" não pode exceder esse valor.  

**Editar um anel**

1. Navegue até a guia **Anéis** .
1. Clique no anel para excluir.  
1. Clique **em Editar anel**.  
1. Edite o número de dias de distribuição e teste, conforme necessário.

**Excluir um anel**

1. Navegue até a guia **Anéis** .  
1. Clique no anel para excluir.  
1. Clique em **Excluir anel**.  

> [!NOTE]
> Os anéis padrão não podem ser excluídos.  

**Mover salas**

É possível mover salas de um anel para outro de duas maneiras:

1. Navegue até a guia **Anéis** .  
1. Clique no anel do qual você deseja mover salas  
1. Clique em **Mover salas**.  
1. Selecione as salas que você deseja mover na **Lista de Salas**.  
1. Escolha o anel Destino, para o qual as salas selecionadas serão movidas na lista suspensa.  
1. Clique em **Mover salas**.  

**Ou**

1. Abra os detalhes da sala para a sala que você deseja mover (por meio de Incidentes, Salas ou Atualizações -> Salas).
1. Clique na guia **Atualizações**.  
1. Em **Anel Atribuído**, clique em **Alterar**.
1. Na lista suspensa, selecione o novo anel.  
1. Clique **em Atribuir**.

## <a name="automated-updates-visibility-and-control"></a>Atualizações automatizadas: Visibilidade e controle

Atualizações automatizadas no Pro Management orquestram atualizações em toda a sua organização. No entanto, você tem a visibilidade e o controle para intervir, se necessário. Aqui estão as maneiras: 

- No caso de uma falha de atualização, um tíquete é gerado automaticamente para acompanhamento. 
- Se você vir uma atualização causando problemas, poderá pausar a atualização com o botão **Pausar** . Clicar no botão Pausa solicitará a criação de um tíquete De registro de problema para sua equipe investigar.
- Se você vir que uma atualização falhou em uma sala e tiver corrigido um motivo plausível, como a desconexão de rede, poderá repetir a atualização com **o botão Repetir tudo com falha** .  
- Pode haver situações urgentes quando você pode decidir disponibilizar uma atualização anteriormente. Nesse caso, você pode usar o botão **Forçar atualizações** . Ao usar a opção Force Update, você tem a opção de forçar a atualização imediatamente ou quando o próximo a sala estiver disponível.  

> [!NOTE]
> **Não recomendamos "Forçar Atualizações"** como uma estratégia geral de gerenciamento de atualizações, pois você pode encontrar problemas conhecidos com essas atualizações.

- Além disso, para garantir boas práticas de gerenciamento de alterações, registraremos todas as atualizações de força internamente no serviço. No futuro, esperamos tornar isso visível para você também.
