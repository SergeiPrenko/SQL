 1. Сколько студентов учатся на втором курсе и более старших курсах? - SELECT * FROM STUDENTS WHERE course >= 2
 2. Сколько студентов мужского пола? -- SELECT * FROM STUDENTS WHERE GENDER = 'm'
 3. Скольких студенток зовут Ольга? -- SELECT * FROM STUDENTS WHERE NAME = 'Ольга'
 4. Скольких студентов зовут не Ольга, и не Виталий и не Дмитрий? -- SELECT * FROM STUDENTS WHERE NAME != 'Ольга' and NAME != 'Виталий' and NAME != 'Дмитрий'
 5. Скольких студентов зовут или Ольга, или Виталий, или Дмитрий? -- SELECT * FROM STUDENTS WHERE NAME = 'Ольга' or NAME = 'Виталий' or NAME = 'Дмитрий'
 6. Сколько преподавателей в таблице LECTURERS из г. Остергард и из университета с ID (UNIV_ID) = 6? -- SELECT * FROM LECTURERS WHERE CITY = 'Остергард' AND UNIV_ID =  6
 7. Сколько студентов из городов Зернотаун, Лемуров, Айфончиков И со второго по четвёртый курс? -- SELECT * FROM STUDENTS WHERE CITY in ('Зернотаун', 'Лемуров', 'Айфончиков') AND COURSE BETWEEN 2 and 4
 8. Сколько уникальных городов в списке преподавателей? -- SELECT DISTINCT CITY FROM LECTURERS
 9. Какая сумма рейтинга (RATING) университетов (UNIVERSITIES) из городов Зернотаун и Лемуров? -- SELECT SUM(RATING) FROM UNIVERSITIES WHERE CITY IN ('Зернотаун', 'Лемуров')
 10. Какой средний балл у студента с фамилией Винник? -- SELECT SURNAME, avg(MARK) FROM EXAM_MARKS JOIN STUDENTS on STUDENT_ID = STUDENTS.id WHERE SURNAME = 'Винник'
 11. Выведите список университетов, в которых меньше всего преподавателей. -- SELECT UNIVERSITIES.NAME, COUNT(LECTURERS.SURNAME) FROM UNIVERSITIES JOIN LECTURERS on UNIVERSITIES.ID = LECTURERS.UNIV_ID GROUP by UNIVERSITIES.NAME
 12. Сколько преподавателей преподают информатику? -- SELECT count(SUBJECTS.NAME) FROM SUBJECTS JOIN SUBJ_LECT on SUBJECTS.ID = SUBJ_LECT.SUBJ_ID JOIN LECTURERS on LECTURERS.ID = SUBJ_LECT.LECTURER_ID WHERE SUBJECTS.NAME = 'Информатика'