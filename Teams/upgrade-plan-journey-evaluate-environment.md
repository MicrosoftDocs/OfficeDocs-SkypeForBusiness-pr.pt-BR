---
title: Atualização do Microsoft Teams | Avaliação do ambiente, perguntas sobre a descoberta
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Use esta orientação para saber mais sobre os requisitos para a avaliação adequada do ambiente atual para a atualização do teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aba20df95071abe3308c9646d04b3a2d898d4ad
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523284"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Avaliar o ambiente antes de atualizar para o Microsoft Teams

![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme que você concluiu essas atividades dos estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Este artigo fornece uma visão geral dos requisitos para a avaliação adequada do ambiente atual para as equipes operacionais. Ao avaliar seu ambiente, você identifica os riscos e os requisitos que influenciarão sua implantação geral. Ao identificar esses itens antecipadamente, você pode ajustar o planejamento para impulsionar o sucesso.

## <a name="introduction-to-the-discovery-questionnaire"></a>Introdução ao questionário de descoberta

Para obter seus resultados de chave objetiva (OKRs), você anteriormente fez decisões importantes sobre o serviço. A próxima etapa é executar a descoberta ambiental para avaliar todos os aspectos relacionados à sua infraestrutura de ti, à rede e às operações para confirmar se a sua organização está pronta para implementar a solução. A descoberta é uma das principais etapas que você faz ao planejar sua jornada para o Teams. A descoberta ambiental deve incluir uma avaliação de prontidão de rede para garantir que a sua rede possa dar suporte à atualização para o Microsoft Teams. Você executa uma descoberta detalhada do seu ambiente para compreender melhor seu estado atual e para revelar qualquer dificuldade ou, ainda mais importante, aos bloqueadores de execução de sua distribuição de suas equipes.

Você identifica riscos técnicos como parte de uma avaliação de avaliação de adoção e avaliação ambiental e desenvolve um plano de mitigação para cada risco identificado. Você deve incorporar essas informações no registro de risco.

Todas as questões relacionadas à sua infraestrutura de colaboração existente e à organização do Office 365, à rede, a pontos de extremidade, às operações e à adoção e à preparação são incluídas como parte do questionário de descoberta ambiental. O questionário é dividido em várias seções para confirmar a preparação da sua organização para a implantação de suas equipes em várias áreas principais. Trabalhe com sua equipe de projeto para fornecer as informações solicitadas com o máximo de detalhes possível para facilitar suas atividades de planejamento.

> [!TIP]
> Você pode começar copiando o questionário em um documento do Microsoft Word. Tente responder a todas as perguntas e capturar todos os detalhes durante a mudança.

## <a name="project-team"></a>Equipe do projeto

Certifique-se de ter participado das pessoas certas para a sua equipe de projeto. Verifique as etapas que você concluiu em [inscrever seus participantes do projeto](upgrade-enlist-stakeholders.md).

## <a name="office-365-organization-details"></a>Detalhes da organização do Office 365

É altamente recomendável que você tenha uma organização ativa do Office 365 enquanto trabalha com este questionário. Se você ainda não ativou ou configurou uma organização do Office 365, confira [planejar a configuração do Office 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use a tabela a seguir para capturar informações sobre a organização do Office 365.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Observe a organização do Office 365 em produção <br>nome e ID na coluna de resposta <br/>Se você tiver mais de um locatário <br>associados à sua organização, <br>Anote todas as IDs. | Nome do locatário: <br/>ID do locatário:| |
> | Em quais regiões os locatários foram implantados?| | |
> | São estes locatários do Office 365 multilocatário ou <br>Dedicar? | <input type="checkbox">Multilocatário<br/> <input type="checkbox">Dedicar | |
> | Quais produtos Microsoft Online estão em uso no momento? <br/>Observe o número de usuários habilitados para cada <br>serviço na coluna comentários. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Demais| |
> | Qual nível de licença está habilitado para o Skype para <br>Usuários do Business Online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Autônoma | O número de usuários <br>para cada SKU: |
> | O que é a floresta atual do Active Directory <br>nível funcional no ambiente? <br/>Se houver mais de uma floresta, observe os detalhes <br>na coluna comentários. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | O que você está usando para o diretório <br>sincronização hoje? |<input type="checkbox">Sem sincronização (somente na nuvem) <br/> <input type="checkbox">Active Directory do Azure <br>&nbsp;&nbsp; &nbsp; Conectado <br/> <input type="checkbox">Outro (especificar na <br>&nbsp;&nbsp; &nbsp; Coluna comentários.)| |
> | A identidade federada está implantada no momento? <br/>(Serviços de Federação do Active Directory ou <br>terceiros) | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se você estiver usando identidade federada, qual é o <br>infraestrutura de Federação? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federação de terceiros <br>&nbsp;&nbsp; &nbsp; Gateway <br>&nbsp;&nbsp; &nbsp; (Observe os detalhes na <br>&nbsp;&nbsp; &nbsp; Coluna comentários.) | |
> | Se você atualmente mantém uma atividade do Office 365 <br>locatário, é o domínio SMTP/SIP do seu <br>usuários direcionados associados ao locatário? | <input type="checkbox">N/d – sem Office 365 <br>&nbsp;&nbsp; &nbsp; locatário no local <br/> <input type="checkbox">Não, SMTP/SIP dos usuários <br>&nbsp;o &nbsp; &nbsp; domínio não está associado <br>&nbsp;&nbsp; &nbsp; com qualquer locatário em <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sim, SMTP/SIP dos usuários <br>&nbsp;&nbsp; &nbsp; domínio está associado <br>&nbsp;&nbsp; &nbsp; com um locatário existente <br>&nbsp;&nbsp; &nbsp; no Office 365 | |
> | Os UPNs do usuário correspondem ao endereço SMTP principal? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Está inconsistente | |

## <a name="existing-collaboration-platform-summary"></a>Resumo da plataforma de colaboração existente

Use a tabela a seguir para capturar informações sobre a implantação da plataforma de colaboração existente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | O Microsoft Teams está implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | O Skype for Business está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br>Você anota a versão e a atualização cumulativa (RECOR) <br>detalhes na coluna comentários. | <input type="checkbox">Sim, Office 365 <br/> <input type="checkbox">Sim, híbrido (com o Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O Exchange está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br>Você anota a versão e a RECOR detalhes nos comentários <br>coluna. | <input type="checkbox">Sim, Office 365 <br/> <input type="checkbox">Sim, híbrido (com o Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado <br>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O SharePoint está implantado? <br/>Para implantações locais e híbridas, certifique-se de que <br>Você anota a versão e a RECOR detalhes nos comentários <br>coluna. | <input type="checkbox">Sim, Office 365 <br/> <input type="checkbox">Sim, híbrido (com o Office 365) <br/> <input type="checkbox">Sim, local <br/> <input type="checkbox">Sim, online, dedicada <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado <br>&nbsp;&nbsp; &nbsp; (terceiros) <br/> <input type="checkbox">Não, outros | |
> | O Office 365 OneDrive for Business está implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você tem outros plataformas de terceiros implantadas <br>e em uso hoje? Em caso afirmativo, anote o número de usuários do <br>essas plataformas e os detalhes de uso nos comentários <br>coluna. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Desperdiça <br/> <input type="checkbox">Outro (especificar nos comentários <br>&nbsp;&nbsp; &nbsp; coluna.) | Número de usuários: <br/>Os|
> | Você pretende mover os usuários dessas pessoas de terceiros <br>plataformas para o Teams? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | O que é a solução de telefonia e conferência atual <br>dos usuários que estão no escopo dessa iniciativa? | | |
> | Você tem o [SBCS que dá suporte ao roteamento direto](direct-routing-plan.md#supported-session-border-controllers-sbcs) implantado para seus escritórios que estão no escopo dessa iniciativa? <br>Em caso afirmativo, observe os detalhes na coluna comentários.| <input type="checkbox">Sim <br/> <input type="checkbox">Não ||

## <a name="collaboration-platform-deployment-details"></a>Detalhes da implantação da plataforma de colaboração

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se aplicável)

Se aplicável, capture os detalhes de sua implantação de equipes usando a tabela de exemplo abaixo. Se você ainda não implantou o Microsoft Teams, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Microsoft Teams? | <input type="checkbox">Todos os usuários da organização <br/> <input type="checkbox">Usuários/grupos de usuários específicos <br>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários) ||
> | Quais recursos e modalidades de equipe estão em uso? | <input type="checkbox">Conversas baseadas em canais <br/> <input type="checkbox">Chat privado <br/> <input type="checkbox">Acesso de convidado <br/> <input type="checkbox">Reuniões de canal <br/> <input type="checkbox">Reuniões privadas <br/> <input type="checkbox">Chamadas privadas <br/> <input type="checkbox">Canal ad-hoc Meetup <br/> <input type="checkbox">Vídeos em reuniões <br/> <input type="checkbox">Compartilhamento de tela em reuniões <br/> <input type="checkbox">Conferência de áudio <br/><input type="checkbox">Aplicativos (aplicativos)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Efetua<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Alinha<br><input type="checkbox">Integração personalizada do armazenamento em nuvem <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, Sharefile, Google Drive, Egnyte (disponível em breve) <br/> <input type="checkbox">Integração de email de canal <br/> <input type="checkbox">Outro (especificar na coluna comentários.) | |
> | Quais aplicativos você implantou para o Microsoft Teams? | | |
> | Você bloqueou especificamente alguma funcionalidade do Microsoft Teams? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Quais clientes Microsoft Teams estão em uso? | <input type="checkbox">Pela <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Macintosh <br/> <input type="checkbox">SS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quem tem permissões para criar equipes? | <input type="checkbox">Todos na organização <br>&nbsp;&nbsp; &nbsp; (Essa é a configuração padrão) <br/> <input type="checkbox">Pessoas específicas <br>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários.) | |
> | Você está usando os recursos de segurança e conformidade do Microsoft Teams? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se aplicável)

Se aplicável, capture os detalhes da sua implantação do Skype for Business online usando a tabela de exemplo abaixo. Se você ainda não implantou a implantação do Skype for Business Online, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Skype <br>para negócios online? | <input type="checkbox">Todos os usuários da organização <br/> <input type="checkbox">Usuários/grupos de usuários específicos <br>&nbsp;&nbsp; &nbsp; (Especificar na coluna comentários) | |
> | Quais recursos e modalidades estão no momento <br>em uso hoje? | <input type="checkbox">Mensagens instantâneas e presença (IM/P)<br/> <input type="checkbox">Treinamento <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Conferência de áudio da Microsoft <br/> <input type="checkbox">Conferência de áudio de terceiros <br>&nbsp;&nbsp; &nbsp; (Observe os detalhes na coluna comentários.) <br/> <input type="checkbox">Planos de chamada (antigo chamada PSTN) <br/> <input type="checkbox">Atendedores automáticos organizacionais <br/> <input type="checkbox">Filas de chamadas | |
> | Você bloqueou especificamente qualquer Skype para <br>Recursos comerciais online? <br>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Qual método você está usando ou planeja usar para <br>conectar o sistema telefônico (anteriormente Cloud PBX) a <br>a PSTN? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Planos de chamada (antigo chamada PSTN) <br/> <input type="checkbox">Conectividade PSTN local (aproveitando o existente <br>&nbsp;&nbsp; &nbsp; Skype for Business 2015 ou Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; implantação) <br/> <input type="checkbox">Conectividade PSTN local (usando o conector de nuvem) | |
> | Você fez a portabilidade de algum número de telefone para a Microsoft? <br/>Isso se aplica a planos de chamada e áudio <br>Recursos de conferência. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business local (se aplicável)

Se aplicável, capture os detalhes da sua implantação do Skype for Business usando a tabela de exemplo abaixo. Se você ainda não implantou o Skype for Business local, pule esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais versões do Lync ou do Skype for Business atualmente <br>foram implantados no local? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Edição do Skype for Business Cloud Connector | |
> | A implantação híbrida o Skype for Business Online está configurada? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Esse ambiente é hospedado e gerenciado por terceiros? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Quais recursos e modalidades estão em uso no momento <br>anunciou? | <input type="checkbox">Mensagens instantâneas e presença (IM/P) <br/> <input type="checkbox">Treinamento <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Chat em grupo/chat persistente <br/> <input type="checkbox">Conferência de áudio da Microsoft <br>&nbsp;&nbsp; &nbsp; (anteriormente discagem em conferência) em seu <br>&nbsp;&nbsp; &nbsp; Lync Server local ou <br>&nbsp;&nbsp; &nbsp; Implantação do Skype for Business <br/> <input type="checkbox">Conferência de áudio de terceiros <br>&nbsp;&nbsp; &nbsp; (Observe os detalhes na coluna comentários) <br/> <input type="checkbox">Enterprise Voice usando PSTN local <br>&nbsp;&nbsp; &nbsp; conectividade <br/> <input type="checkbox">Planos de chamada (antes chamadas PSTN) via <br>&nbsp;&nbsp; &nbsp; Híbrido com o Skype for Business Online | |
> | Quais versões do Servidor de Borda você tem implantadas? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | Você tem o Lync ou o Skype for Business Edge implantado <br>em mais de um datacenter? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Selecione os serviços que a sua função de borda fornece hoje. | <input type="checkbox">Acesso de usuários externos (usuários corporativos) <br/> <input type="checkbox">Acesso de usuário remoto (anônimo anônimo <br>&nbsp;&nbsp; &nbsp; participantes da reunião) <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Retransmissão de mídia | |
> | Qual dos seguintes recursos de chamada de voz você <br>atualmente tem dependências? <br/>Observação de qualquer dependência adicional nos comentários <br>coluna. | <input type="checkbox">Opções de ocupado <br/> <input type="checkbox">Estacionamento de chamadas <br/> <input type="checkbox">Recebimento de chamadas ou retirada de chamadas em grupo <br/> <input type="checkbox">Celulares comuns ou "divisão de mesa" <br/> <input type="checkbox">Grupos de respostas ou grupos de busca <br/> <input type="checkbox">Aparência da linha compartilhada <br/> <input type="checkbox">Linha particular <br/> <input type="checkbox">Caixa <br/> <input type="checkbox">Ligar via trabalho <br/> <input type="checkbox">Números de emergência ou informações <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox">Discagem de extensão <br/> <input type="checkbox">Atendedor automático <br/> <input type="checkbox">Acesso do assinante <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Mascaramento de identificação de chamadas ou alteração <br/> <input type="checkbox">Roteamento baseado em local <br/> <input type="checkbox">Roteamento de menor custo <br/> <input type="checkbox">Telefones do elevador | |

## <a name="networking-and-access-to-office-365-services"></a>Rede e acesso aos serviços do Office 365

Use a tabela a seguir para capturar os detalhes da rede da sua organização e como os usuários estão (ou serão) conectados aos serviços do Office 365.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Como fazer (ou quais serão) os usuários em escopo para a migração <br>acessar o Microsoft Teams quando ele estiver no escritório? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Conexão NAT roteada <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Wi-Fi público <br/> <input type="checkbox">Wi-Fi gerenciado (não público) <br/> <input type="checkbox">ExpressRoute (emparelhamento da Microsoft) ||
> | Se o acesso ao Office 365 é por meio de um servidor proxy, há <br>alguma maneira de ignorar o proxy? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | A Rota Expressa está sendo usada atualmente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Não, mas está sendo planejada | |
> | Você realizou uma avaliação de prontidão de rede? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Os usuários precisam usar uma VPN quando se conectam ao <br>recursos corporativos remotamente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se for usada uma VPN, o tráfego do teams pode ser excluído do <br>a VPN para acessar serviços do Office 365 diretamente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Sua rede dá suporte a QoS? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você pode priorizar o tráfego de áudio e vídeo das equipes <br>para impulsionar uma experiência de alta qualidade? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Todos os locais dentro de uma região têm egresso na Internet, <br>ou é um egresso na Internet centralizado para toda a região? | <input type="checkbox">Acesso regional à Internet <br/> <input type="checkbox">Acesso centralizado à Internet | |

## <a name="endpoints"></a>Pontos de extremidade

Use a tabela a seguir para capturar os detalhes dos clientes e pontos de extremidade em uso.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que sistema operacional de área de trabalho os usuários estão utilizando? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (especifique a versão na coluna comentários). <br/> <input type="checkbox">Linux (especifica a distribuição na coluna comentários). <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual versão do Microsoft Office foi implantada <br>para estes dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual tecnologia de implantação do Office está em uso <br>em sua organização? | <input type="checkbox">MSI <br/> <input type="checkbox">Clique para executar | |
> | Quais são os dispositivos móveis permitidos e compatíveis <br>plataformas em uso? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Windows <br/> <input type="checkbox">Celular <br/> <input type="checkbox">SS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Como os dispositivos móveis são fornecidos? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Dispositivos corporativos <br/> <input type="checkbox">Traga seu próprio dispositivo | |
> | Quais dispositivos os usuários usam atualmente para acessar <br>serviços de voz e conferência <br>(aparelhos de telefone, fones de ouvido, telefones, vídeo)? | | |

## <a name="operations"></a>Operações

Use a tabela a seguir para capturar os detalhes dos aspectos operacionais do seu ambiente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o modelo de operações do Lync Server <br>Skype for Business Server ou implantação do Office 365 <br>anunciou? | | |
> | Você pode estruturar a organização de suporte atual para <br>Lync Server, Skype for Business Server ou Office 365? | | |
> | Se você estiver implantando em vários países ou regiões, <br>cada país/região tem sua própria conta/telefonia <br>pessoal para trabalhar ou isso será gerenciado centralmente? | <input type="checkbox">Suporte e operações regionais <br/> <input type="checkbox">Operações centralizadas e suporte | |
> | Você está acompanhando a [metodologia de qualidade da chamada](quality-of-experience-review-guide.md)? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você atribuiu uma pessoa ou equipe ao <br>Função de especialista em qualidade para a plataforma de colaboração <br>em uso? | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Como você monitora o Lync Server, Skype para <br>Business Server ou implantação do Office 365? | | |
> | Você tem problemas de qualidade das chamadas? | <input type="checkbox">Sim<br/> <input type="checkbox">Não | |
> | Como e quando você fornece treinamento para seu <br>assistência técnica sobre novos serviços e recursos? | | |

## <a name="adoption-and-readiness"></a>Adoção e preparação

Use a tabela a seguir e registre o estado atual de adoção e preparação de sua organização.

>
> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o seu uso ativo atual de <br>Skype for Business? | **_ _** % total de usuários ativos versus usuários habilitados | |
> | Como a sua organização usa <br>Skype for Business? | Conversas privadas <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> COMUNICAR <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamou <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br> Reuniões <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferência<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamou | |
> | Sua organização tem uma adoção do usuário <br>e a equipe de gerenciamento de alterações? | <input type="checkbox">Sim<br/> <input type="checkbox">Não | |
> | Como você atualmente mede o sucesso do sucesso para a tecnologia <br>distribuições como o Skype for Business? | | |
> | Qual a porcentagem de sua base de usuários que você diria <br>adotou o Skype for Business? | | |
> | Qual é a opinião dos usuários a respeito do Skype for Business? | <input type="checkbox">Corretamente <br/> <input type="checkbox">Neutra <br/> <input type="checkbox">Mal | |
> | Qual das opções a seguir melhor descreve a distribuição <br>estratégia usada para seu Skype for Business <br>implementação? | <input type="checkbox">Grande alcance: campanha de E-mail com <br>&nbsp;&nbsp; &nbsp; links para treinamento <br/> <input type="checkbox">Expandido: amplo alcance mais uma variedade <br>&nbsp;&nbsp; &nbsp; campanhas de conscientização (cartazes, <br>&nbsp;&nbsp; &nbsp; eventos, campeões) e treinamento <br>&nbsp;&nbsp; &nbsp; (vídeos, guias do usuário, em pessoa) <br/> <input type="checkbox">Personalizado: expandido e mais direcionado <br>&nbsp;&nbsp; &nbsp; mensagens e treinamentos por pessoa <br/> <input type="checkbox">Demais <br>&nbsp;&nbsp; &nbsp; (Observe os detalhes na coluna comentários.) | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul><li>Quem será o responsável pela conclusão de uma avaliação de ambiente?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Próxima etapa</td><td><ul><li>Documentar os resultados da avaliação do ambiente.</li></ul></td></tr>
</table>

Depois de avaliar seu ambiente, prossiga para a próxima etapa: [preparar sua rede](prepare-network.md).
