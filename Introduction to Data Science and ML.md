ВТОРОЙ РАЗДЕЛ КУРСА "Введение в Data Science и машинное обучение", 2.6, 5/6
                                                                        20.02.2024
##GridSearchCV##

#Импортировали библиотеки
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import GridSearchCV

clf = DecisionTreeClassifier() #Инициализация дерева
paramerts = {"criterion": ["gini", "entropy"], "max_depth": range(1, 30)} #Выбираем параметры
search_parametrs_clf = GridSearchCV(clf, paramerts, cv=5) # Получили данные, по выбранным выше параметрам
search_parametrs_clf.fit(X_train, y_train) #Обучение на тенировочных данных (их я получал заранее)
search_parametrs_clf.best_params_ #получение лучших параметров
best_clf.score(X_test, y_test) #получение результата на тестовых параметрах


from sklearn.metrics import precision_score, recall_score
y_pred = best_clf.predict(X_test)
#Получили precision и recall на основе лучших результатов на тестовых параметрах
precision_score(y_test, y_pred)
recall_score(y_test, y_pred)


y_pridicted_prob = best_clf.predict_proba(X_test) #































