# Imutabilidade

# O que é?

Imutabilidade é a característica de um objeto que após criado não pode ser modificado, permanecendo inalterado durante todo seu ciclo de vida. 

# Vantagens

Com dados imutáveis as funções não podem alterar o estado dos objetos e consequentemente não possui efeitos colaterais, permitindo que os softwares tenham resultados mais seguros e previsíveis. As estruturas imutáveis são recomendadas para trabalhar com concorrência, visto que não há necessidade de sincronização, tornando seguro o compartilhamento de objetos em diferentes threads. Imutabilidade pode ajudar na simplicidade da escrita de testes unitários, pois como os objetos não mudam de estado não é necessário criar testes que cobrem diversas possibilidades devido a mutação.

# Desvantagens

Quando se trabalha com estruturas de dados muito grandes pode haver um alto custo de memória na aplicação, visto que para cada modificação necessária na estrutura, deve-se criar uma cópia alterando a informação desejada e considerando várias cópias de muito dados pode afetar no desempenho.