# fc2-graphql

Exemplos:

mutation createCategory {
  createCategory(
    input: {
      name: "PHP",
      description: "PHP is awesome"
    }
  ) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(
    input: {
      name: "Evolving with PHP",
      description: "Mega PHP is awesome"
      categoryId: "T5577006791947779410"
    }
  ) {
    id
    name
    description
    category {
      id
      name
    }
  }
}

mutation createChapter {
  createChapter(
    input: {
      name: "Evolving with PHP",
      courseId: "T8674665223082153551"
    }
  ) {
    id
    name
    course {
      id
      name
    }
  }
}

query findCategories {
  categories {
    id
    name
    description
    courses {
      name
      description
    }
  }
}

query findCourses {
  courses {
    id
    name
    description
    chapters {
      id
      name
    }
    category {
      id
      name
    }
  }
}

query findChapters {
  chapters {
    id
    name
    course {
      id
      name
    }
  }
}

