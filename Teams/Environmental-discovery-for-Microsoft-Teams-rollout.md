---
title: Descoberta de ambiente para uma distribuição Teams da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Como executar uma descoberta ambiental detalhada à medida que você planeja sua jornada do Skype para negócios a Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e5ad44dcdca1d72fb21dba5c0c3a3d98a50dcc9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372117"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Descoberta de ambiente para uma distribuição Teams da Microsoft
===================================================

Descoberta é uma das etapas muito primeiras, chaves que você tomar ao planejar sua jornada para Teams da Microsoft.

Executar uma descoberta detalhada do seu ambiente para entender melhor o estado atual e revelar qualquer dificuldades ou — ainda mais — bloqueadores possíveis para a execução da sua distribuição de equipes.

<a name="discovery-questionnaire"></a>Questionário de descoberta
=======================

O questionário de amostra abaixo o orienta durante um conjunto de perguntas para confirmar que sua organização está pronta para a distribuição bem-sucedida do sistema telefônico e conferência de áudio com os recursos de chamada planos em equipes.

Todos os assuntos relacionados ao seu existente infraestrutura de colaboração e locatário do Office 365, rede, pontos de extremidade, operações e adoção e preparação são incluídos como parte do questionário descoberta ambiental.

O questionário é dividido em várias seções para confirmar a preparação da sua organização para sua implantação de equipes em várias áreas principais. Trabalhar com sua equipe de projeto para fornecer as informações solicitadas com tantos detalhes forem possíveis para facilitar suas atividades de planejamento.

> [!TIP]
> Você pode iniciar, copiando o questionário em um documento do Microsoft Word. Tente responder todas as perguntas e capturar todos os detalhes de como você percorre.

<a name="project-team"></a>Equipe de projeto
------------

Capture informações detalhadas sobre os principais participantes do seu projeto de implementação de equipes. Observe que uma pessoa pode desempenhar várias funções em todo o projeto.

> | Função                                  | Nome, endereço de email, número de telefone | Local, fuso horário | Comentários      |
> |---------------------------------------|-----------------------------------|---------------------|---------------|
> | Patrocinador executivo                     |                                   |                     |               |
> | Líder de projeto                          |                                   |                     |               |
> | Líder/arquiteto de colaboração          |                                   |                     |               |
> | Consultor                            |                                   |                     |               |
> | Gerente de projetos                       |                                   |                     |               |
> | Especialista em adoção/gerenciamento de mudanças |                                   |                     |               |
> | Líder de rede                          |                                   |                     |               |
> | Líder de segurança                         |                                   |                     |               |
> | Líder de telefonia                        |                                   |                     |               |
> | Líder de desktop                          |                                   |                     |               |
> | Líder de suporte/suporte técnico                |                                   |                     |               |
> | Líder de implantação                       |                                   |                     |               |
> | Proprietário do serviço                         |                                   |                     |               |
> | Líder de instalações                       |                                   |                     |               |
> | Líder da equipe de vídeo                       |                                   |                     |               |
> | Líderes de unidade de negócios                   |                                   |                     |               |

<a name="office-365-tenant-details"></a>Detalhes de Inquilino do Office 365
-------------------------

É altamente recomendável que você tenha um locatário do Office 365 ativo enquanto você trabalha com este questionário. Se você ainda não tiver ativado ou ainda configurado um locatário do Office 365, consulte [planejar sua instalação do Office 365 para empresas](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use a tabela a seguir para capturar informações sobre o locatário do Office 365.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Observe o locatário de produção Office 365 <br>nome e a identificação da coluna de resposta <br/>Se você tiver mais de um inquilino <br>associado à sua organização, <br>Observe que todos os IDs.  | Nome do locatário: <br/>ID do inquilino:| |
> | Em quais regiões os locatários são implantados?| | |
> | São esses inquilinos multi-Inquilinos do Office 365 ou <br>Dedicado? | <input type="checkbox">Multi-inquilinos<br/> <input type="checkbox">Dedicada | |
> | Quais produtos Microsoft Online estão em uso no momento? <br/>Observe o número de usuários habilitados para cada um <br>serviço na coluna comentários. | <input type="checkbox">Equipes da Microsoft <br/> <input type="checkbox">Skype para negócios <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Outros|                                   |
> | Qual nível de licença está habilitado para Skype para <br>Usuários Online de negócios? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | O número de usuários <br>para cada SKU: |
> | Qual é a floresta do Active Directory atual <br>nível funcional no ambiente? <br/>Se houver mais de uma floresta, observe os detalhes <br>na coluna comentários. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | O que você está usando para o diretório <br>sincronização hoje? |<input type="checkbox">Nenhum sync (somente nuvem) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Conectar <br/> <input type="checkbox">Outros (especifique na <br>&nbsp;&nbsp; &nbsp;Coluna comentários.)| |
> | A identidade federada está implantada no momento? <br/>(Serviços de Federação do active Directory ou <br>terceiros) | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se você estiver usando a identidade federada, qual é o <br>infraestrutura de Federação? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federação de terceiros <br>&nbsp;&nbsp; &nbsp;gateway <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes do <br>&nbsp;&nbsp; &nbsp;Coluna comentários.) | |
> | Se você mantiver atualmente um ativo do Office 365 <br>locatários, é o domínio SMTP/SIP da sua <br>direcionados os usuários associados com o locatário? | <input type="checkbox">N/d – sem o Office 365 <br>&nbsp;&nbsp; &nbsp;locatário in-loco <br/> <input type="checkbox">Não, SMTP/SIP dos usuários <br>&nbsp;&nbsp; &nbsp;domínio não está associado <br>&nbsp;&nbsp; &nbsp;com qualquer locatários em <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sim, SMTP/SIP dos usuários <br>&nbsp;&nbsp; &nbsp;domínio está associado <br>&nbsp;&nbsp; &nbsp;com um locatário existente <br>&nbsp;&nbsp; &nbsp;no Office 365 | |
> | Usuário UPNs coincidem seu endereço SMTP principal? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Modo inconsistente | |

<a name="existing-collaboration-platform-summary"></a>Plataforma de colaboração existente resumida
---------------------------------------

Use a tabela a seguir para capturar informações sobre a implantação de plataforma de colaboração existente.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | O Microsoft Teams está implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | O Skype for Business está implantado? <br/>Para o local e híbrido implantações, certifique-se <br>você observar a versão e a atualização cumulativa (CU) <br>detalhes na coluna comentários. | <input type="checkbox">Sim, o Office 365 <br/> <input type="checkbox">Sim, híbrida (com o Office 365) <br/> <input type="checkbox">Sim, no local <br/> <input type="checkbox">Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sim, hospedados, dedicada <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhado (terceiros) <br/> <input type="checkbox">Nenhum, outros | |
> | O Exchange está implantado? <br/>Para o local e híbrido implantações, certifique-se <br>você observar a versão e CU detalhes nos comentários <br>coluna. | <input type="checkbox">Sim, o Office 365 <br/> <input type="checkbox">Sim, híbrida (com o Office 365) <br/> <input type="checkbox">Sim, no local <br/> <input type="checkbox">Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sim, hospedados, dedicada <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhada <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox">Nenhum, outros | |
> | O SharePoint está implantado? <br/>Para o local e híbrido implantações, certifique-se <br>você observar a versão e CU detalhes nos comentários <br>coluna. | <input type="checkbox">Sim, o Office 365 <br/> <input type="checkbox">Sim, híbrida (com o Office 365) <br/> <input type="checkbox">Sim, no local <br/> <input type="checkbox">Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Sim, hospedados, dedicada <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox">Sim, hospedado, compartilhada <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox">Nenhum, outros | |
> | É o Office 365 OneDrive for Business implantado? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você tem outras plataformas de terceiros implantadas <br>e, em uso atualmente? Em caso afirmativo, observe o número de usuários do <br>Essas plataformas e os detalhes de uso nos comentários <br>coluna. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Margem de atraso <br/> <input type="checkbox">Outros (Especifique nos comentários <br>&nbsp;&nbsp; &nbsp;coluna.) | Número de usuários: <br/>Detalhes:|
> | Você está planejando mover usuários desses softwares de terceiros <br>plataformas às equipes? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Qual é a solução de conferência e telefonia atual <br>os usuários que fazem parte do escopo essa iniciativa? | | |
> | Você tem [SBC que dê suporte direto de roteamento](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) implantados para seus escritórios que fazem parte do escopo essa iniciativa? <br>Em caso afirmativo, observe os detalhes na coluna comentários.| <input type="checkbox">Sim <br/> <input type="checkbox">Não ||

<a name="collaboration-platform-deployment-details"></a>Detalhes de implantação de plataforma de colaboração
-----------------------------------------

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se aplicável)

Se aplicável, capture os detalhes da sua implantação de equipes, usando a tabela de exemplo abaixo. Se você ainda não implantou as equipes, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Que tipos de usuários estão habilitados para o Microsoft Teams? | <input type="checkbox">Todos os usuários na organização <br/> <input type="checkbox">Grupos de usuários/usuários específicos <br>&nbsp;&nbsp; &nbsp;(Especificar na coluna comentários) ||
> | Quais recursos de equipes e modalidades estão em uso? | <input type="checkbox">Conversas de canal <br/> <input type="checkbox">Bate-papo privado <br/> <input type="checkbox">Acesso de convidado <br/> <input type="checkbox">Reuniões de canal <br/> <input type="checkbox">Reuniões privadas <br/> <input type="checkbox">Chamada privada <br/> <input type="checkbox">Meetup de canal da ad hoc <br/> <input type="checkbox">Vídeos em reuniões <br/> <input type="checkbox">Tela de compartilhamento em reuniões <br/> <input type="checkbox">Serviços de audioconferência <br/><input type="checkbox">Aplicativos (apps)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Guias<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conectores<br><input type="checkbox">Integração do armazenamento de nuvem personalizado <br>&nbsp;&nbsp; &nbsp; (Caixa, pasta de recados, ShareFile, Google unidade) <br/> <input type="checkbox">Integração de email de canal <br/> <input type="checkbox">Outros (especifique na coluna comentários). | |
> | Quais aplicativos você implantou a equipes? | | |
> | Você bloqueou especificamente alguma funcionalidade do Microsoft Teams? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Quais clientes Microsoft Teams estão em uso? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Quem tem permissões para criar equipes? | <input type="checkbox">Todas as pessoas na organização <br>&nbsp;&nbsp; &nbsp;(Que é a configuração padrão) <br/> <input type="checkbox">Pessoas específicas <br>&nbsp;&nbsp; &nbsp;(Especificar na coluna comentários). | |
> | Você está usando os recursos de segurança e conformidade do Microsoft Teams? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se aplicável)

Se aplicável, capture os detalhes do seu Skype para implantação Business Online usando-se a tabela de exemplo abaixo. Se você ainda não implantou Skype para implantação Business Online, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quais tipos de usuários estão habilitados para Skype <br>para negócios Online? | <input type="checkbox">Todos os usuários na organização <br/> <input type="checkbox">Grupos de usuários/usuários específicos <br>&nbsp;&nbsp; &nbsp;(Especificar na coluna comentários) | |
> | Quais modalidades e recursos estão atualmente <br>em uso atualmente? | <input type="checkbox">Mensagens instantâneas e presença (IM/P)<br/> <input type="checkbox">Conferência <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Conferência de áudio da Microsoft <br/> <input type="checkbox">Serviços de audioconferência de terceiros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna comentários.) <br/> <input type="checkbox">Planos de chamada (anteriormente PSTN chamar) <br/> <input type="checkbox">Atendedores automáticos organizacional <br/> <input type="checkbox">Filas de chamada | |
> | Você especificamente bloqueou qualquer Skype para <br>Recursos Online de negócios? <br>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Método que são você usando ou planeja usar para <br>Conecte-se o sistema telefônico (anteriormente nuvem PBX) para <br>PSTN? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Planos de chamada (anteriormente PSTN chamar) <br/> <input type="checkbox">Conectividade PSTN (como aproveitar existente no local <br>&nbsp;&nbsp; &nbsp;Skype para negócios 2015 ou o Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;implantação) <br/> <input type="checkbox">Conectividade PSTN local (usando o conector de nuvem) | |
> | Você fez a portabilidade de algum número de telefone para a Microsoft? <br/>Isso é aplicável aos planos de chamada e áudio <br>Recursos de conferência. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype para negócios local (se aplicável)

Se aplicável, capture os detalhes do seu Skype para implantação de negócios usando a tabela de exemplo abaixo. Se você ainda não implantou Skype para negócios local, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Quais versões do Lync ou Skype for Business no momento <br>são implantados no local? | <input type="checkbox">O Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">O Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype para Business Server 2015 <br/> <input type="checkbox">Skype para o conector de nuvem Business Edition | |
> | A implantação híbrida o Skype for Business Online está configurada? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Esse ambiente hospedado e gerenciado por um terceiro? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Quais modalidades e os recursos estão sendo usados <br>hoje? | <input type="checkbox">Mensagens instantâneas e presença (IM/P) <br/> <input type="checkbox">Conferência <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Gravação de reunião <br/> <input type="checkbox">Bate-papo persistente / bate-papo de grupo <br/> <input type="checkbox">Conferência de áudio da Microsoft <br>&nbsp;&nbsp; &nbsp;(anteriormente discar conferência) em sua <br>&nbsp;&nbsp; &nbsp;do Lync Server no local ou <br>&nbsp;&nbsp; &nbsp;Skype para implantação de negócios <br/> <input type="checkbox">Serviços de audioconferência de terceiros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna comentários) <br/> <input type="checkbox">Usando o Enterprise Voice local PSTN <br>&nbsp;&nbsp; &nbsp;conectividade <br/> <input type="checkbox">Planos de chamada (anteriormente PSTN chamar) via <br>&nbsp;&nbsp; &nbsp;Híbrida com Skype para negócios on-line | |
> | Quais versões do Servidor de Borda você tem implantadas? | <input type="checkbox">O Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">O Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype para Business Server 2015 | |
> | Você tem Lync ou Skype para borda de negócios implantado <br>em mais de um datacenter? <br/>Em caso afirmativo, observe os detalhes na coluna comentários. | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Selecione os serviços que sua função de borda fornece hoje. | <input type="checkbox">Acesso de usuário externo (usuários corporativos) <br/> <input type="checkbox">Acesso de usuário remoto (anônimo externo <br>&nbsp;&nbsp; &nbsp;os participantes da reunião) <br/> <input type="checkbox">Federação <br/> <input type="checkbox">Retransmissão de mídia | |
> | Quais do seguinte recursos de chamada de voz faça você <br>atualmente tem dependências? <br/>Observe quaisquer dependências adicionais nos comentários <br>coluna. | <input type="checkbox">Opções de disponibilidade <br/> <input type="checkbox">Estacionamento de chamada <br/> <input type="checkbox">Chamar retirada ou retirada de chamada de grupo <br/> <input type="checkbox">Telefones de área comum ou "hot desking" <br/> <input type="checkbox">Grupos de resposta ou grupos de busca <br/> <input type="checkbox">Aparência da linha compartilhada <br/> <input type="checkbox">Linha privada <br/> <input type="checkbox">Caixa postal <br/> <input type="checkbox">Chamada via trabalho <br/> <input type="checkbox">Números de emergência ou informações <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Discagem de ramais <br/> <input type="checkbox">Atendedor automático <br/> <input type="checkbox">Acesso do assinante <br/> <input type="checkbox">Dispositivos analógicos <br/> <input type="checkbox">Fax <br/> <input type="checkbox">Mascaramento de ID de chamador ou alterar <br/> <input type="checkbox">Roteamento baseado no local <br/> <input type="checkbox">Roteamento de custo mínimo <br/> <input type="checkbox">Telefones elevador | |

<a name="networking-and-access-to-office-365-services"></a>Rede e acesso aos serviços do Office 365
--------------------------------------------

Use a tabela a seguir para capturar detalhes de rede da sua organização e como os usuários são (ou estará) conectados aos serviços do Office 365.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Tutorial (ou como) os usuários no escopo de migração <br>acessar as equipes quando eles estão no escritório? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Conexão de NAT roteado <br/> <input type="checkbox">Servidor proxy <br/> <input type="checkbox">Público Wi-Fi <br/> <input type="checkbox">Gerenciada Wi-Fi (não pública) <br/> <input type="checkbox">ExpressRoute (Microsoft correspondência) ||
> | Se o acesso ao Office 365 é por meio de um servidor proxy, há <br>nenhuma maneira para ignorar o proxy? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | A Rota Expressa está sendo usada atualmente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não <br/> <input type="checkbox">Não, mas está sendo planejado | |
> | Você executou uma avaliação de prontidão da rede? <br/>Para obter mais informações, consulte [Avaliação de prontidão de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Os usuários precisam usar uma VPN para se conectar a <br>recursos corporativos remotamente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Se for usada uma VPN, pode tráfego equipes sejam excluído do <br>VPN para acessar os serviços do Office 365 diretamente? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Sua rede dá suporte a QoS? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você pode priorizar o tráfego de áudio e vídeo de equipes <br>para conduzir a uma experiência de alta qualidade? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Todos os locais dentro de uma região que possuem a saída de internet <br>ou é centralizada de saída da internet para toda a região? | <input type="checkbox">Regional acesso à internet <br/> <input type="checkbox">Centralizado acesso à internet | |

> [!TIP]
> Para calcular a quantidade de largura de banda e outros requisitos de rede para sua voz nuvem implantação, dependendo de detalhes da sua organização e o uso estimado, visite [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) em [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

<a name="endpoints"></a>Pontos de extremidade
---------

Use a tabela a seguir para obter os detalhes de como os clientes e pontos de extremidade em uso.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Que sistema operacional de área de trabalho os usuários estão utilizando? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (especificar a versão na coluna comentários). <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual versão do Microsoft Office é implantado <br>para esses dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Qual tecnologia de implantação do Office está em uso <br>em sua organização? | <input type="checkbox">MSI <br/> <input type="checkbox">Click-to-Run | |
> | Quais são os permitidos e suporte móveis <br>plataformas em uso? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Outros (Observe os detalhes na coluna comentários.) | |
> | Como os dispositivos móveis são fornecidos? <br/>Selecione todas as opções que se aplicam. | <input type="checkbox">Dispositivos corporativos <br/> <input type="checkbox">Traga seu próprio dispositivo | |
> | Quais dispositivos faça usuários atualmente usar para acessar <br>Serviços de voz e conferência <br>(telefones, headsets, telefones, vídeo)? | | |

<a name="operations"></a>Operações
----------

Use a tabela a seguir para capturar os detalhes dos aspectos operacionais do seu ambiente.

> | Pergunta | Resposta | Comentários |
> |------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
> | Qual é o seu modelo de operações para o Lync Server <br>Skype para Business Server ou implantação do Office 365 <br>hoje? | | |
> | Você contorno disposição para suporte atual <br>Lync Server, Skype para Business Server ou o Office 365? | | |
> | Se você estiver implantando em vários países ou regiões, <br>cada país/região tem seu próprio IT / telefonia <br>para trabalhar com da equipe ou serão isso gerenciados centralmente? | <input type="checkbox">Suporte e operações regionais <br/> <input type="checkbox">Suporte e operações centralizadas | |
> | Você está acompanhando a Metodologia de Qualidade da Chamada? | <input type="checkbox">Sim <br/> <input type="checkbox">Não | |
> | Você atribuiu um indivíduo ou de equipe para o <br>Função campeões de qualidade para a plataforma de colaboração <br>Além de usar? | <input type="checkbox">Sim <br/> <input type="checkbox">Não ||
> | Como você para monitorar seu servidor do Lync, Skype para <br>Servidor de negócios ou Office 365 implantação? | | |
> | Você tem problemas de qualidade das chamadas? | <input type="checkbox">Sim<br/> <input type="checkbox">Não | |
> | Como e quando você fornecer treinamento para seu <br>assistência técnica em novos serviços e recursos? | | |

<a name="adoption-and-readiness"></a>Preparação e adoção
----------------------

Use a tabela a seguir e registre o estado atual de adoção e preparação de sua organização.

> 
> |                                                    Pergunta                                                     |                                                                                                                                                                                                                                                                                      Resposta                                                                                                                                                                                                                                                                                      | Comentários |
> |-----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
> |                          Qual é o seu uso ativo atual do <br>Skype para os negócios?                           |                                                                                                                                                                                                                                                                 % **_** total usuários ativos versus usuários habilitados                                                                                                                                                                                                                                                                 |          |
> |                             Como a sua organização está usando <br>Skype para os negócios?                              |                                                                                                   Conversas privadas <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Mensagens Instantâneas <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Chamar <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Compartilhamento<br> Reuniões <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Conferência<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Compartilhamento<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Chamar                                                                                                   |          |
> |                   Sua organização tem a adoção de um usuário <br>e a equipe de gerenciamento de alterações?                   |                                                                                                                                                                                                                                                           <input type="checkbox">Sim<br/> <input type="checkbox">Não                                                                                                                                                                                                                                                            |          |
> |            Como você medir o êxito da tecnologia atualmente <br>distribuições like Skype para os negócios?            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |               Porcentagem da Base de dados de usuário seria disse tem <br>adotado Skype para os negócios?               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |          |
> |                                Qual é a opinião dos usuários a respeito do Skype for Business?                                |                                                                                                                                                                                                                                       <input type="checkbox">BOM <br/> <input type="checkbox">Neutro <br/> <input type="checkbox">Ruim                                                                                                                                                                                                                                       |          |
> | Qual destas opções melhor descreve a distribuição <br>estratégia usada para seu Skype para negócios <br>implantação? | <input type="checkbox">Amplo alcance: campanha de E-mail com <br>&nbsp;&nbsp; &nbsp;links para treinamento <br/> <input type="checkbox">Expandido: Uma variedade mais amplo alcance <br>&nbsp;&nbsp; &nbsp;de campanhas de divulgação (cartazes, <br>&nbsp;&nbsp; &nbsp;eventos, campeões) e treinamento <br>&nbsp;&nbsp; &nbsp;(vídeos, guias do usuário, pessoalmente) <br/> <input type="checkbox">Adaptados: Expandida, além de direcionado <br>&nbsp;&nbsp; &nbsp;mensagens e treinamento por pessoa <br/> <input type="checkbox">Outros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna comentários.) |          |
